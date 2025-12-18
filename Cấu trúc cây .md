#include <iostream>

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
int main()
{
    Node* p = new Node;
    p = tao_node(100);
    them_trai(p, 5);
    them_phai(p, 10);
    them_trai(p->left, 1024);
    them_phai(p->left, 101);
    them_trai(p->right, 50);
    them_phai(p->right, 5000);
    Ktra_rong(p) ? std::cout << "Cay rong\n" : std::cout << "Cay khong rong\n";
    std::cout << "Duyet truoc: ";
    duyet_truoc(p);
    std::cout << "\n";
    std::cout << "Duyet giua: ";
    duyet_giua(p);
    std::cout << "\n";
    std::cout << "Duyet sau: ";
    duyet_sau(p);
    trả về 0;
}
