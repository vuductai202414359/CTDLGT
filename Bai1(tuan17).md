#include <iostream>
#include <vector>
#include <string>
#include <algorithm>

sử dụng không gian tên std;

cấu trúc Node {
    tiêu đề chuỗi; // Mục tiêu đề
    trang int; // Số trang của mục đó (hoặc tổng số trang)
    vector<Node*> con; // Danh sách các mục

    Node(string t, int p) : title(t), pages(p) {}
};

int dem_trang(Node* root) {
    nếu (!root) trả về 0;
    return root->children.size();
}


int tong_trang(Node* node) {
    int total = node->pages;
    for (Node* child : node->children) {
        tổng += tong_trang(child);
    }
    Tổng số tiền trả lại;
}


Node* chuong_dai_nhat(Node* root) {
    if (!root || root->children.empty()) return nullptr;

    Node* longest = nullptr;
    int maxPages = -1;

    for (Node* chapter : root->children) {
        int currentTotal = tong_trang(chapter);
        nếu (currentTotal > maxPages) {
            maxPages = currentTotal;
            dài nhất = chương;
        }
    }
    Trả về giá trị dài nhất;
}


bool xoa(Node* parent, string targetTitle) {
    for (auto it = parent->children.begin(); it != parent->children.end(); ++it) {
        nếu ((*it)->title == targetTitle) {
            Xóa nó đi;
            cha->con.xóa(nó);
            Trả về giá trị đúng;
        }
        if (xoa(*it, targetTitle)) return true;
    }
    Trả về false;
}


void tim_chuong(Node* root, string chapterTitle) {
    for (Node* chapter : root->children) {
        nếu (chapter->title == chapterTitle) {
            cout << "Cac muc trong chuong '" << chapTitle << "':" << endl;
            nếu (chapter->children.empty()) {
                cout << "- Không có mục con." << kết thúc;
            }
            khác {
                for (Node* section : chapter->children) {
                    cout << "+ " << section->title << " (" << section->pages << " trang)" << endl;
                }
            }
            trở lại;
        }
    }
    cout << "Khong tim thay chuong: " << chapTitle << endl;
}

int main() {
    Node* book = new Node("Giao trinh C++", 0);

    Node* c1 = Node mới("Chương 1: Cô ban", 10);
    Node* c2 = new Node("Chương 2: Cau truc du lieu", 15);
    Node* c3 = new Node("Chương 3: Thuật toán", 50);

    book->children.push_back(c1);
    book->children.push_back(c2);
    book->children.push_back(c3);

    c1->children.push_back(new Node("1.1 Biên và Kiều du lieu", 5));
    c1->children.push_back(new Node("1.2 Vong lap", 8));

    cout << "1. So chương của sách: " << dem_trang(book) << endl;

    Nút* dài nhất = chương_dai_nhat(sách);
    if (longest) cout << "2. Chuong dai nhat: " << longest->title << endl;

    cout << "3.";
    tim_chương(sách, "Chương 1: Cô ban");

    cout << "4. Đặng xoa mục '1.1 Biên và Kiều du liễu'..." << endl;
    xoa(sách, "1.1 Biên và Kiều du liễu");

    tim_chương(sách, "Chương 1: Cô ban");

    trả về 0;
}
