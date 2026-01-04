#include <iostream>


cấu trúc Node {
    int data; // chi so
    char a[100]; // mười muc
    Nút* bên trái;
    Nút* bên phải;
};


bool so_sanh_sach(Node* t, Node* h) {
    nếu (t == NULL && h == NULL) {
        Trả về giá trị đúng;
    }
    return (t->data == h->data && so_sanh_cay(t->left, h->left) && so_sanh_cay(t->right, h->right));
}
int main()
{
    Node* p = new Node();
    Node* l = new Node();
    nếu (so_sanh_sach(p, l))
        std::cout << "2 sách giong nhau\n";
    else std::cout << "2 sách khắc nhau\n";
    
	// Đỗ phúc tập của thuật toàn: O(n)
    trả về 0;

}
