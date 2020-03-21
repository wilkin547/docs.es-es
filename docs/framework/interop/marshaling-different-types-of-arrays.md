---
title: Cálculo de referencias de tipos diferentes de matrices
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- marshaling, Arrays sample
- data marshaling, Arrays sample
ms.assetid: c5ac9920-5b6e-4dc9-bf2d-1f6f8ad3b0bf
ms.openlocfilehash: 66c7ba5989952edb55f21aab960ad7395a92ae0d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79181360"
---
# <a name="marshaling-different-types-of-arrays"></a>Cálculo de referencias de tipos diferentes de matrices
Una matriz es un tipo de referencia en código administrado que contiene uno o varios elementos del mismo tipo. Aunque las matrices son tipos de referencia, se pasan como parámetros In a funciones no administradas. Este comportamiento no se corresponde con la manera en que se pasan las matrices administradas a los objetos administrados, que es como parámetros In/Out. Para obtener más información, consulte [Copiar y fijar](copying-and-pinning.md).  
  
 En la tabla siguiente se muestran las opciones de cálculo de referencias de matrices y se describe su uso.  
  
|Array|Descripción|  
|-----------|-----------------|  
|De enteros por valor.|Pasa una matriz de enteros como un parámetro In.|  
|De enteros por referencia.|Pasa una matriz de enteros como un parámetro In/Out.|  
|De enteros por valor (bidimensional).|Pasa una matriz multidimensional de enteros como un parámetro In.|  
|De cadenas por valor.|Pasa una matriz de cadenas como un parámetro In.|  
|De estructuras con enteros.|Pasa una matriz de estructuras que contienen enteros como un parámetro In.|  
|De estructuras con cadenas.|Pasa una matriz de estructuras que solo contienen cadenas como un parámetro In/Out. Los miembros de la matriz se pueden cambiar.|  
  
## <a name="example"></a>Ejemplo  
 En este ejemplo se muestra cómo pasar los siguientes tipos de matrices:  
  
- Matriz de enteros por valor.  
  
- Matriz de enteros por referencia, que se puede cambiar de tamaño.  
  
- Matriz multidimensional de enteros por valor.  
  
- Matriz de cadenas por valor.  
  
- Matriz de estructuras con enteros.  
  
- Matriz de estructuras con cadenas.  
  
 A menos que una matriz se calcule explícitamente por referencia, el comportamiento predeterminado calcula las referencias de la matriz como un parámetro In. Puede cambiar este comportamiento aplicando explícitamente los atributos <xref:System.Runtime.InteropServices.InAttribute> y <xref:System.Runtime.InteropServices.OutAttribute> .  
  
 En el ejemplo Arrays se usan las siguientes funciones no administradas, que se muestran con su declaración de función original:  
  
- **TestArrayOfInts** exportada desde PinvokeLib.dll.  
  
    ```cpp
    int TestArrayOfInts(int* pArray, int pSize);  
    ```  
  
- **TestRefArrayOfInts** exportada desde PinvokeLib.dll.  
  
    ```cpp
    int TestRefArrayOfInts(int** ppArray, int* pSize);  
    ```  
  
- **TestMatrixOfInts** exportada desde PinvokeLib.dll.  
  
    ```cpp
    int TestMatrixOfInts(int pMatrix[][COL_DIM], int row);  
    ```  
  
- **TestArrayOfStrings** exportada desde PinvokeLib.dll.  
  
    ```cpp
    int TestArrayOfStrings(char** ppStrArray, int size);  
    ```  
  
- **TestArrayOfStructs** exportada desde PinvokeLib.dll.  
  
    ```cpp
    int TestArrayOfStructs(MYPOINT* pPointArray, int size);  
    ```  
  
- **TestArrayOfStructs2** exportada desde PinvokeLib.dll.  
  
    ```cpp
    int TestArrayOfStructs2 (MYPERSON* pPersonArray, int size);  
    ```  
  
 [PinvokeLib.dll](marshaling-data-with-platform-invoke.md#pinvokelibdll) es una biblioteca personalizada no administrada que contiene implementaciones de las funciones enumeradas anteriormente y dos variables de estructura: **MYSTRSTRUCT** y **MYSTRSTRUCT2**. Estas estructuras contienen los siguientes elementos:  
  
```cpp
typedef struct _MYPOINT  
{  
   int x;
   int y;
} MYPOINT;  
  
typedef struct _MYPERSON  
{  
   char* first;
   char* last;
} MYPERSON;  
```  
  
 En este ejemplo, las estructuras `MyPoint` y `MyPerson` contienen tipos insertados. El atributo <xref:System.Runtime.InteropServices.StructLayoutAttribute> se establece para garantizar que los miembros se organizan secuencialmente en la memoria, en el orden en que aparecen.  
  
 La clase `NativeMethods` contiene un conjunto de métodos llamados por la clase `App` . Para obtener detalles específicos sobre cómo pasar matrices, consulte los comentarios del ejemplo siguiente. Una matriz, que es un tipo de referencia, se pasa como un parámetro In de forma predeterminada. Para que el llamador reciba los resultados, se deben aplicar **InAttribute** y **OutAttribute** de manera explícita al argumento que contiene la matriz.  
  
### <a name="declaring-prototypes"></a>Declaración de prototipos  
 [!code-csharp[Conceptual.Interop.Marshaling#31](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/arrays.cs#31)]
 [!code-vb[Conceptual.Interop.Marshaling#31](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/arrays.vb#31)]  
  
### <a name="calling-functions"></a>Llamadas a funciones  
 [!code-csharp[Conceptual.Interop.Marshaling#32](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/arrays.cs#32)]
 [!code-vb[Conceptual.Interop.Marshaling#32](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/arrays.vb#32)]  
  
## <a name="see-also"></a>Consulte también

- [Tipos de datos de invocación de plataforma](marshaling-data-with-platform-invoke.md#platform-invoke-data-types)
- [Crear prototipos en código administrado](creating-prototypes-in-managed-code.md)
