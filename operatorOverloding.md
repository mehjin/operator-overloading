# operator-overloading

#include<iostream>
#include<string.h>

class Vector2D {
private:
	int x;
	int y;
public:
	Vector2D(int X, int Y) : x(X), y(Y) { }
	void setX(int X) { x = X; }
	void setY(int Y) { y = Y; }
	int getX() const { return x; }
	int getY() const { return y; }
	friend int operator * (const Vector2D& v1, const Vector2D& v2);
};
      // this?? friend??

int main()
{
	Vector2D A(1, 2); 
	Vector2D B(3, 4);
	
	printf("%d", A * B);
	system("pause");

}
/*
int operator * (const Vector2D& v1, const Vector2D& v2) {
	int v1X = v1.getX();
	int v1Y = v1.getY();
	int v2X = v2.getX();
	int v2Y = v2.getY();
	int temp1 = v1X * v2X;
	int temp2 = v1Y * v2Y;
	
	return temp1 + temp2;
}
*/ 
//교체 코드.
int operator *(const Vector2D& v1, const Vector2D& v2) {
	return (v1.x * v2.x) + (v1.y * v2.y);
}
