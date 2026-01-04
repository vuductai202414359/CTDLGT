
#include <iostream>
#include <vector>
#include <algorithm>
sử dụng không gian tên std;
cấu trúc Node {
    dữ liệu int;
    Nút* bên trái;
    Nút* bên phải;
};

void tao_goc(Node*& t) {
    t = NULL;
}
bool Ktra_rong(Node* t) {
    nếu (t == NULL)
        Trả về giá trị đúng;
    Ngược lại, trả về false;
}

Node* tao_node(int x) {
    Node* p = new Node;
    p->data = x;
    p->left = NULL;
    p->right = NULL;
    trả về p;
}

void them_trai(Node*& t, int x) {
    nếu (t == NULL || t->left != NULL) {
        std::cout << "Không chúng dược\n";
    }
    khác {
        t->left = tao_node(x);
    }
}
void them_phai(Node*& t, int x) {
    nếu (t == NULL || t->right != NULL) {
        std::cout << "Không chúng dược\n";
    }
    khác {
        t->right = tao_node(x);
    }
}

void duyet_truoc(Node* t) {
    nếu (t != NULL) {
        std::cout << t->data << " ";
        duyet_truoc(t->left);
        duyet_truoc(t->right);
    }
}

void duyet_giua(Node* t) {
    nếu (t != NULL) {
        duyet_giua(t->left);
        std::cout << t->data << " ";
        duyet_giua(t->right);
    }
}

void duyet_sau(Node* t) {
    nếu (t != NULL) {
        duyet_sau(t->left);
        duyet_sau(t->right);
        std::cout << t->data << " ";
    }
}
void tao_mang(Node* t, vector<int>& a) {
    nếu (!t) trả về;
    a.push_back(t->data);
    tao_mang(t->left, a);
    tao_mang(t->right, a);
}
void cap_nhat_mang(Node* t, const vector<int>& a, int& i) {
    if (!t || i >= a.size()) return;
    t->data = a[i++];
    cap_nhat_mang(t->left, a, i);
    cap_nhat_mang(t->right, a, i);
}
void vun_dong(vector<int>& a, int n, int i) {
    int maxx = i;
    int l = 2 * i + 1;
    int r = 2 * i + 2;
    nếu (l < n && a[l] > a[maxx])
        maxx = l;
    nếu (r < n && a[r] > a[maxx])
        maxx = r;
    nếu (maxx != i) {
        std::swap(a[i], a[maxx]);
        vun_dong(a, n, maxx);
    }
}
int main()
{
    Node* p = new Node;
    p = tao_node(4);
    them_trai(p, 1);
    them_phai(p, 3);
    them_trai(p->left, 2);
    them_phai(p->left, 16);
    them_trai(p->right, 9);
    them_phai(p->right, 10);
	them_trai(p->left->left, 14);
	them_phai(p->left->left, 8);
	them_trai(p->left->right, 7);
    Ktra_rong(p) ? std::cout << "Cay rong\n" : std::cout << "Cay khong rong\n";
    std::cout << "Duyet truoc: ";
    duyet_truoc(p);
    std::cout << "\n";
    std::cout << "Duyet giua: ";
    duyet_giua(p);
    std::cout << "\n";
    std::cout << "Duyet sau: ";
    duyet_sau(p);
    cout << "\n";
	///Vun dong cay nhi phan
    vector<int> a;
    tao_mang(p, a);
    int n = a.size();
    for (int i=0; i < n; i++) {
        std::cout << a[i] << " ";
	}
	cout << "\n";
    for (int i = n / 2 - 1; i >= 0; i--) {
        vun_dong(a, n, i);
    }
    int i = 0;
    cap_nhat_mang(p, a, i);
    std::cout << "\nCây sau khi vun đồng:\n";
    duyet_truoc(p);
    
    trả về 0;
}
