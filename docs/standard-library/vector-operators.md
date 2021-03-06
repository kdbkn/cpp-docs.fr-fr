---
title: '&lt;vector&gt;, opérateurs | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- vector/std::operator!=
- vector/std::operator&gt;
- vector/std::operator&gt;=
- vector/std::operator&lt;
- vector/std::operator&lt;=
- vector/std::operator==
dev_langs:
- C++
ms.assetid: 1d14f312-6f59-4ec7-88ae-95f89a558823
helpviewer_keywords:
- std::operator!= (vector)
- std::operator&gt; (vector)
- std::operator&gt;= (vector)
- std::operator&lt; (vector)
- std::operator&lt;= (vector)
- std::operator== (vector)
ms.openlocfilehash: 779fe61bec63f55d7f3b8b3bb7f2e0d084fbab5b
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/08/2018
---
# <a name="ltvectorgt-operators"></a>&lt;vector&gt;, opérateurs

||||
|-|-|-|
|[operator!=](#op_neq)|[operator&gt;](#op_gt)|[operator&gt;=](#op_gt_eq)|
|[operator&lt;](#op_lt)|[operator&lt;=](#op_lt_eq)|[operator==](#op_eq_eq)|

## <a name="op_neq"></a>  operator!=

Teste si l’objet situé à gauche de l’opérateur n’est pas égal à l’objet situé à droite.

```cpp
bool operator!=(const vector<Type, Allocator>& left, const vector<Type, Allocator>& right);
```

### <a name="parameters"></a>Paramètres

`left` Un objet de type **vecteur**.

`right` Un objet de type **vecteur**.

### <a name="return-value"></a>Valeur de retour

**true** si les vecteurs ne sont pas égaux ; **false** si les vecteurs sont égaux.

### <a name="remarks"></a>Notes

Deux vecteurs sont égaux s’ils ont le même nombre d’éléments et si leurs éléments respectifs ont les mêmes valeurs. Sinon, elles sont inégales.

### <a name="example"></a>Exemple

```cpp
// vector_op_ne.cpp
// compile with: /EHsc
#include <vector>
#include <iostream>

int main( )
{
   using namespace std;

   vector <int> v1, v2;
   v1.push_back( 1 );
     v2.push_back( 2 );

   if ( v1 != v2 )
      cout << "Vectors not equal." << endl;
   else
      cout << "Vectors equal." << endl;
}
```

```Output
Vectors not equal.
```

## <a name="op_lt"></a>  operator&lt;

Teste si l’objet situé à gauche de l’opérateur est inférieur à l’objet situé à droite.

```cpp
bool operator<(const vector<Type, Allocator>& left, const vector<Type, Allocator>& right);
```

### <a name="parameters"></a>Paramètres

`left` Un objet de type **vecteur**.

`right` Un objet de type **vecteur**.

### <a name="return-value"></a>Valeur de retour

**true** si le vecteur situé à gauche de l’opérateur est strictement inférieur au vecteur situé à droite de l’opérateur ; sinon, **false**.

### <a name="example"></a>Exemple

```cpp
// vector_op_lt.cpp
// compile with: /EHsc
#include <vector>
#include <iostream>

int main( )
{
   using namespace std;

   vector <int> v1, v2;
   v1.push_back( 1 );
   v1.push_back( 2 );
   v1.push_back( 4 );

   v2.push_back( 1 );
   v2.push_back( 3 );

   if ( v1 < v2 )
      cout << "Vector v1 is less than vector v2." << endl;
   else
      cout << "Vector v1 is not less than vector v2." << endl;
}
```

```Output
Vector v1 is less than vector v2.
```

## <a name="op_lt_eq"></a>  operator&lt;=

Teste si l’objet situé à gauche de l’opérateur est inférieur ou égal à l’objet situé à droite.

```cpp
bool operator<=(const vector<Type, Allocator>& left, const vector<Type, Allocator>& right);
```

### <a name="parameters"></a>Paramètres

`left` Un objet de type **vecteur**.

`right` Un objet de type **vecteur**.

### <a name="return-value"></a>Valeur de retour

**true** si le vecteur situé à gauche de l’opérateur est inférieur ou égal au vecteur situé à droite de l’opérateur ; sinon, **false**.

### <a name="example"></a>Exemple

```cpp
// vector_op_le.cpp
// compile with: /EHsc
#include <vector>
#include <iostream>

int main( )
{
   using namespace std;

   vector <int> v1, v2;
   v1.push_back( 1 );
   v1.push_back( 2 );
   v1.push_back( 4 );

   v2.push_back( 1 );
   v2.push_back( 3 );

   if ( v1 <= v2 )
      cout << "Vector v1 is less than or equal to vector v2." << endl;
   else
      cout << "Vector v1 is greater than vector v2." << endl;
}
```

```Output
Vector v1 is less than or equal to vector v2.
```

## <a name="op_eq_eq"></a>  operator==

Teste si l’objet situé à gauche de l’opérateur est égal à l’objet situé à droite.

```cpp
bool operator==(const vector<Type, Allocator>& left, const vector<Type, Allocator>& right);
```

### <a name="parameters"></a>Paramètres

`left` Un objet de type **vecteur**.

`right` Un objet de type **vecteur**.

### <a name="return-value"></a>Valeur de retour

**true** si le vecteur situé à gauche de l’opérateur est égal au vecteur situé à droite de l’opérateur ; sinon, **false**.

### <a name="remarks"></a>Notes

Deux vecteurs sont égaux s’ils ont le même nombre d’éléments et si leurs éléments respectifs ont les mêmes valeurs. Sinon, elles sont inégales.

### <a name="example"></a>Exemple

```cpp
// vector_op_eq.cpp
// compile with: /EHsc
#include <vector>
#include <iostream>

int main( )
{
   using namespace std;

   vector <int> v1, v2;
   v1.push_back( 1 );
   v2.push_back( 1 );

   if ( v1 == v2 )
      cout << "Vectors equal." << endl;
   else
      cout << "Vectors not equal." << endl;
}
```

```Output
Vectors equal.
```

## <a name="op_gt"></a>  operator&gt;

Teste si l’objet situé à gauche de l’opérateur est supérieur à l’objet situé à droite.

```cpp
bool operator>(const vector<Type, Allocator>& left, const vector<Type, Allocator>& right);
```

### <a name="parameters"></a>Paramètres

`left` Un objet de type **vecteur**.

`right` Un objet de type **vecteur**.

### <a name="return-value"></a>Valeur de retour

**true** si le vecteur situé à gauche de l’opérateur est supérieur au vecteur situé à droite de l’opérateur ; sinon, **false**.

### <a name="example"></a>Exemple

```cpp
// vector_op_gt.cpp
// compile with: /EHsc
#include <vector>
#include <iostream>

int main( )
{
   using namespace std;

   vector <int> v1, v2;
   v1.push_back( 1 );
   v1.push_back( 3 );
   v1.push_back( 1 );

   v2.push_back( 1 );
   v2.push_back( 2 );
   v2.push_back( 2 );

   if ( v1 > v2 )
      cout << "Vector v1 is greater than vector v2." << endl;
   else
      cout << "Vector v1 is not greater than vector v2." << endl;
}
```

```Output
Vector v1 is greater than vector v2.
```

## <a name="op_gt_eq"></a>  operator&gt;=

Teste si l’objet situé à gauche de l’opérateur est supérieur ou égal à l’objet situé à droite.

```cpp
bool operator>=(const vector<Type, Allocator>& left, const vector<Type, Allocator>& right);
```

### <a name="parameters"></a>Paramètres

`left` Un objet de type **vecteur**.

`right` Un objet de type **vecteur**.

### <a name="return-value"></a>Valeur de retour

**true** si le vecteur situé à gauche de l’opérateur est supérieur ou égal au vecteur situé à droite de l’opérateur ; sinon, **false**.

### <a name="example"></a>Exemple

```cpp
// vector_op_ge.cpp
// compile with: /EHsc
#include <vector>
#include <iostream>

int main( )
{
   using namespace std;

   vector <int> v1, v2;
   v1.push_back( 1 );
   v1.push_back( 3 );
   v1.push_back( 1 );

     v2.push_back( 1 );
   v2.push_back( 2 );
   v2.push_back( 2 );

   if ( v1 >= v2 )
      cout << "Vector v1 is greater than or equal to vector v2." << endl;
   else
      cout << "Vector v1 is less than vector v2." << endl;
}
```

```Output
Vector v1 is greater than or equal to vector v2.
```

## <a name="see-also"></a>Voir aussi

[\<vector>](../standard-library/vector.md)<br/>
