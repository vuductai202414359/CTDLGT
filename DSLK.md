#include <iomanip>

struct Sinh_vien {
    int MSSV;
    int Nam_sinh;
    double GPA;
	char ho_ten[30];
};
struct SV {
    Sinh_vien s;
	SV* next;
};
typedef struct SV* sv;

sv tao_sv(Sinh_vien s) {
    sv tmp = new SV();
    tmp->s = s;
    tmp->next = NULL;
	return tmp;
}
void in(sv h) {
    sv p = h; 
	std::cout << "Danh sach sinh vien:\n";
    while (p != NULL) {
        std::cout << p->s.MSSV << " " << p->s.Nam_sinh << " " << p->s.ho_ten << " ";
        std::cout << std::fixed << std::setprecision(2) << p->s.GPA << std::endl;
		p = p->next;
    }
}
int Do_dai(sv h) {
    sv p = h;
    int dem = 0;
    while (p != NULL) {
        dem++;
        p = p->next;
    }
    return dem;
}
int dem_sl_GPA(double x, sv h) {
    sv p = h; 
    int dem = 0;
    while (p != NULL) {
        if (p->s.GPA > x) {
            dem++;
        }
        p = p->next;
    }
    return dem;
}
void chen_dau(sv& h, Sinh_vien s) {
    sv tmp = tao_sv(s); 
    if (h == NULL) {
        h = tmp;
    }
    else {
        tmp->next = h;
        h = tmp;
    }
}
void chen_cuoi(sv& h, Sinh_vien s) {
	sv tmp = tao_sv(s);
    if (h == NULL) {
        h = tmp; 
    }
    else {
        sv p = h;
        while (p->next != NULL) {
            p = p->next;
        }
        p->next = tmp;
    }
}
void chen_GPA(sv& h, Sinh_vien s) {
    sv tmp = tao_sv(s);
    if (h == NULL) {
        h = tmp;
    }
    else {
        sv p = h;
        while (p->next != NULL && p->next->s.GPA < tmp->s.GPA) {
            p = p->next;
        }
		tmp->next = p->next;
		p->next = tmp;
    }
}
void sap_xep_GPA(sv& h) {
    for (sv p = h; p != NULL; p = p->next) {
        sv minsv = p;
        for (sv q = p->next; q != NULL; q = q->next) {
            if (q->s.GPA < minsv->s.GPA) {
                minsv = q;
			}
        }
		Sinh_vien tmp = p->s;
        p->s = minsv->s;
        minsv->s = tmp;
    }
}
int main()
{
    Sinh_vien s1 = { 202414128, 2006, 4.0, "HuyHoang"};
	Sinh_vien s2 = { 202414129, 2005, 3.6, "SonDao"};
    Sinh_vien s3 = { 202414130, 2005, 3.0, "BachXuan"};
	Sinh_vien s4 = { 202414131, 2006, 1.8, "TaiTuaOcCho" };
    sv h = tao_sv(s1);
    sv head = h;
	h->next = tao_sv(s2);
	h->next->next = tao_sv(s3);
    h->next->next->next = tao_sv(s4);
    in(h);
    std::cout << "Do dai cua day sinh vien la : " << Do_dai(head) << "\n";
    std::cout << "So luong sinh vien co GPA > 3.2 la : " << dem_sl_GPA(3.2, head) << "\n";
    sap_xep_GPA(head);
    in(head);
	Sinh_vien s5 = { 202414132, 2007, 2.4, "Hoang" };
	chen_GPA(head, s5);
    in(head);
	return 0;
}
