#include <iostream>

#define null -1
cấu trúc Cay {
    int a[100];
    số nguyên n;
};

void rong(Cay &t) {
    for (int i = 0; i < 100; i++) {
        ta[i] = -1;
    }
}

bool ktra_rong(Cay t) {
    nếu (ta[0] == -1)
        Trả về giá trị đúng;
    Ngược lại, trả về false;
}

void them_goc(Cay& t, int x) {
    nếu (ktra_rong(t)) {
        ta[0] = x;
        tn = 1;
    }
    else std::cout << "Khong chúng duoc\n";
}

// them vao node co chi so i
void them_trai(Cay& t, int i, int x) {
    int l = 2 * i + 1;
    nếu (ta[i] == -1) {
        std::cout << "Không chúng dược\n";
    }
    khác {
        ta[l] = x;
    }
}

void them_phai(Cay& t, int i, int x) {
    int r = 2 * i + 2;
    nếu (ta[i] == -1) {
        std::cout << "Không chúng dược\n";
    }
    khác {
        ta[r] = x;
    }
}

void duyet_truoc(Cây& t, int i) {
    nếu (ta[i] != -1 && i < 100) {
        std::cout << ta[i] << " ";
        duyet_truoc(t, i * 2 + 1);
        duyet_truoc(t, i * 2 + 2);
    }
}

void duyet_giua(Cây& t, int i) {
    nếu (ta[i] != -1 && i < 100) {
        duyet_giua(t, i * 2 + 1);
        std::cout << ta[i] << " ";
        duyet_giua(t, i * 2 + 2);
    }
}

void duyet_sau(Cây& t, int i) {
    nếu (ta[i] != -1 && i < 100) {
        duyet_sau(t, i * 2 + 1);
        duyet_sau(t, i * 2 + 2);
        std::cout << ta[i] << " ";
    }
}
int main() {
    Cay t;
    rong(t);
    them_goc(t, 100);
	them_trai(t, 0, 5);
	them_phai(t, 0, 10);
	them_trai(t, 1, 1024);
	them_phai(t, 1, 101);
	them_trai(t, 2, 50);
    them_phai(t, 2, 50000);
	ktra_rong(t) ? std::cout << "Cay rong\n" : std::cout << "Cay khong rong\n";
	std::cout << "Duyet truoc: ";
	duyet_truoc(t, 0);
	std::cout << "\n";
	std::cout << "Duyet giua: ";
	duyet_giua(t, 0);
	std::cout << "\n";
	std::cout << "Duyet sau: ";
	duyet_sau(t, 0);
    trả về 0;
}
