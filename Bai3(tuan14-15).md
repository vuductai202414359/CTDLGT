#include <iostream>
sử dụng không gian tên std;

// Cấu hình một nút trên cây
cấu trúc Node {
    int value; // Giá trị nút
    Nút* trái; // Con trỏ tới nút bên trái
    Nút* bên phải; // Con trỏ tới nút phải

    // Hàm tạo
    Node(int v, Node* l = NULL, Node* r = NULL) {
        giá trị = v;
        trái = l;
        phải = r;
    }
};

// Tìm kiếm phân tích nhị phân lớp
lớp BSTree {
riêng tư:
    Gốc nút*;

    // Hàm xóa cây trống (viết theo quy tắc kiểu đệ quy)
    void makeEmpty(Node*& t) {
        nếu (t != NULL) {
            makeEmpty(t->left);
            makeEmpty(t->right);
            xóa t;
        }
        t = NULL;
    }

    // Hàm chèn một nút mới (viết theo kiểu đệ quy)
    void insert(int val1, Node*& t) {
        nếu (t == NULL) {
t = new Node(val1);
        }
        ngược lại nếu (val1 < t->value) {
            chèn(val1, t->trái);
        }
        nếu (val1 > t->value) {
            chèn(val1, t->phải);
        }
    }

    // Hàm tìm kiếm nút (viết theo kiểu đệ quy)
    Node* search(int val2, Node* t) {
        nếu (t == NULL) trả về NULL;
        if (val2 < t->value) return search(val2, t->left);
        if (val2 > t->value) return search(val2, t->right);
        trả về t; // Tìm thấy
    }

công cộng:
    // Hàm tạo (cấm đầu cây trống)
    BSTree() {
        gốc = NULL;
    }

    // Hàm hủy bỏ (xóa hết các nút trên cây)
    ~BSTree() {
        makeEmpty(root);
    }

    // Kiểm tra cây có trống hay không
    bool isEmpty() {
        return root == NULL;
    }

    // Xóa các nút trên cây
    void makeEmpty() {
        makeEmpty(root);
    }

    // Chèn một nút mới vào cây
    void insert(int val1) {
        chèn(val1, root);
    }

    // Tìm nút có giá trị val2
    Node* search(int val2) {
        trả về tìm kiếm(val2, root);
    }

    // Hàm get gốc để sử dụng cho các hàm bên ngoài của trình duyệt
    Node* getRoot() {
        trả về gốc;
    }
};

// --- Các cây chức năng (Yêu cầu bổ sung) ---

// Duyệt thứ tự tiền (Pre-order): Root -> Left -> Right
void PREORDER_travl(Node* t) {
    nếu (t != NULL) {
        cout << t->value << " ";
        PREORDER_travl(t->left);
        PREORDER_travl(t->right);
    }
}

// Duyệt thứ tự (Theo thứ tự): Left -> Root -> Right
void INORDER_travl(Node* t) {
    nếu (t != NULL) {
        INORDER_travl(t->left);
        cout << t->value << " ";
        INORDER_travl(t->right);
    }
}

// Duyệt Hậu thứ tự (Theo thứ tự sau): Left -> Right -> Root
void POSTORDER_travl(Node* t) {
    nếu (t != NULL) {
        POSTORDER_travl(t->left);
        POSTORDER_travl(t->right);
        cout << t->value << " ";
    }
}

int main() {
    BSTree bst;

    // Chèn các nút có giá trị theo yêu cầu vào ảnh
    bst.insert(5);
    bst.insert(6);
    bst.insert(3);
    bst.insert(8);
    bst.insert(7);
    bst.insert(4);
    bst.insert(2);

    // root để trình duyệt
    Node* root = bst.search(5);

    cout << "Duyet cay thu tu truoc (Pre-order):" << endl;
    PREORDER_travl(root);
    cout << endl;

    // Tìm hai nút có giá trị 4 và 9
    Node* n1 = bst.search(4);
    Node* n2 = bst.search(9);

    // Trong kết quả tìm kiếm
    nếu (n1 != NULL)
        cout << "Node co gia tri bang 4 la " << n1->value << endl;

    nếu (n2 == NULL)
        cout << "Không tìm thay" << endl;

    // Làm việc với cây
    bst.makeEmpty();
    nếu (bst.isEmpty())
        cout << "Cay da bi xoa rong" << endl;

    trả về 0;
}
