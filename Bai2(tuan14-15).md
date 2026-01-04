#include <iostream>


cấu trúc Node {
    dữ liệu int;
    Nút* bên trái;
    Nút* bên phải;
};

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

bool so_sanh_cay(Node* t, Node* h) {
    nếu (t == NULL && h == NULL) {
        Trả về giá trị đúng;
    }
    return (t->data == h->data && so_sanh_cay(t->left, h->left) && so_sanh_cay(t->right, h->right));
}
int main()
{
    Node* p = new Node();
    Node* l = new Node();
    nếu (so_sanh_cay(p, l))
        std::cout << "2 cây giồng nhau\n";
    else std::cout << "2 cay khắc nhau\n";
    p->data = 5;
    l->data = 4;
    nếu (so_sanh_cay(p, l))
        std::cout << "2 cây giồng nhau\n";
    else std::cout << "2 cay khắc nhau\n";
    trả về 0;

}
