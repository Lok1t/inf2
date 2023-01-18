#include <iostream>
#include <vector>
#include <math.h>
#include <algorithm>
using namespace std;
vector<string> v = { "r1", "r2", "i1", "r3", "i2", "i3", "i4" };

int getS(string s, int n) {
	int ans = 0;
	for (int i = pow(2, n - 1) - 1; i < s.size(); i += pow(2, n)) {
		for (int j = 0; j < pow(2, n - 1); j++) {
			if (i + j < s.size()) ans += s[i + j];
		}
	}
	return ans % 2;
}

void print(string s, int broken) {
	for (int i = 2; i < s.size(); i++) {
		if (i == 3) continue;
		cout << v[i] << " = " << s[i] << endl;
	}

	if (broken == 0) cout << "\nNo errors detected.";
	else cout << "\nError was in " << v[broken - 1] << ".";

}

bool isCorrect(string code) {
	if (code.size() != 7) return false;
	for (char c : code) {
		if (c != '0' && c != '1') return false;
	}
	return true;
}

int main() {
	string s;
	cin >> s;

	if (!isCorrect(s)) {
		cout << "Input is incorrect.";
		return 0;
	}

	int s1 = getS(s, 1);
	int s2 = getS(s, 2);
	int s3 = getS(s, 3);

	int broken = s3 * 4 + s2 * 2 + s1;

//	out << broken << endl;

	if (broken == 0) print(s, 0);
	else {
		s[broken - 1] = (s[broken - 1] == '1' ? '0' : '1');
		print(s, broken);
	}
	cout << endl << s1 << " " << s2 << " " << s3;
}
