## 函数模板
利用函数重载特性对不同类型实现相同功能
```CPP
//int类型
void addTo(int a[], int b[], int size){
     for(int i = 0; i < size; i++) b[i] += a[i];
}

//long类型
void addTo(long a[], long b[], int size){
     for(int i = 0; i < size; i++) b[i] += a[i];
}

//float
void addTo(float a[], float b[], int size){
     for(int i = 0; i < size; i++) b[i] += a[i];
}

//double
void addTo(double a[], double b[], int size){
     for(int i = 0; i < size; i++) b[i] += a[i];
}
```
利用函数模板实现相同功能
```CPP
//函数模板
template <class T>
void addTo(T a[], T b[], int size){
     for(int i = 0; i < size; i++) b[i] += a[i];
}

//编译系统将依据每一次对函数模板调用时实际所使用的数据类型生成适当的调用代码，并生成相应的函数版本
unsigned x,y;

//函数模板的实例化，三种形式等价
addTo<unsigned>(x, y, 9);    //未省略模板实参表
addTo< >(x, y, 9);           //省略模板实参表中的实参，从模板函数实参表推断类型
addTo(x, y, 9);              //完全省略模板实参表，自动推断类型
//模板实参表的优先级高于模板函数实参表
```
## 类模板
