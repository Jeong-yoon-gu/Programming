# Programming
간단한 프로그래밍 공부
(피보나치 함수)
int fibonacci(int n) {
    if (n == 0) {
        printf("0");
        return 0;
    } else if (n == 1) {
        printf("1");
        return 1;
    } else {
        return fibonacci(n‐1) + fibonacci(n‐2);
    }
}
ibonacci(3)은 fibonacci(2)와 fibonacci(1) (첫 번째 호출)을 호출한다.
fibonacci(2)는 fibonacci(1) (두 번째 호출)과 fibonacci(0)을 호출한다.
두 번째 호출한 fibonacci(1)은 1을 출력하고 1을 리턴한다.
fibonacci(0)은 0을 출력하고, 0을 리턴한다.
fibonacci(2)는 fibonacci(1)과 fibonacci(0)의 결과를 얻고, 1을 리턴한다.
첫 번째 호출한 fibonacci(1)은 1을 출력하고, 1을 리턴한다.
fibonacci(3)은 fibonacci(2)와 fibonacci(1)의 결과를 얻고, 2를 리턴한다.

#include <stdio.h>
void printMenu()
{
printf("==========================\n");
printf(" 'c' 섭씨온도에서 화씨온도로 변환\n");
printf(" 'f' 화씨온도에서 섭씨온도로 변환\n");
printf(" 'q' 종료\n");
printf("==========================\n");
}
double C2F(double c_temp)
{
return 9.0 / 5.0 * c_temp + 32;
}
double F2C(double f_temp)
{
return (f_temp - 32.0) * 5.0 / 9.0;
}
int main(void)
{
char choice;
double temp;
while (1) {
printMenu();
printf("메뉴에서 선택하세요: ");
choice = getchar();
if (choice == 'q') break;
else if (choice == 'c') {
printf("섭씨온도: ");
scanf("%lf", &temp);
printf("화씨온도: %lf \n\n", C2F(temp));
}
else if (choice == 'f') {
printf("화씨온도: ");
scanf("%lf", &temp);
printf("섭씨온도: %lf \n\n", F2C(temp));
}
getchar(); // 엔터키 문자를 삭제하기 위하여 필요!
}
return 0;
}

// 수학적인 조합 값을 구하는 예제
#include <stdio.h>
// 팩토리얼 값을 반환
int factorial(int n)
{
int i, result = 1;
for (i = 1; i <= n; i++)
result *= i; // result = result * i
return result;
}
// 팩토리얼 값을 이용하여서 조합값을 계산
int combination(int n, int r)
{
return (factorial(n)/(factorial(r) * factorial(n-r)));
}
// 사용자로부터 값을 입력받아서 반환
int get_integer(void)
{
int n;
printf("정수를 입력하시오: ");
scanf("%d", &n);
return n;
}
int main(void)
{
int a, b;
a = get_integer();
b = get_integer();
printf("C(%d, %d) = %d \n", a, b, combination(a, b));
return 0;
}
