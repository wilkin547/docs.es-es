---
title: "Aplicar la conversión boxing a tipos que aceptan valores NULL (Guía de programación de C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- boxing [C#], nullable types
- unboxing [C#], nullable types
- nullable types [C#], boxing and unboxing
ms.assetid: bdb5b626-abc0-405d-8f64-0f0a0bf883a4
caps.latest.revision: 12
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 5ce063a70ced98fd8b99b4b46d704e08ddc96e10
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="boxing-nullable-types-c-programming-guide"></a>Aplicar la conversión boxing a tipos que aceptan valores NULL (Guía de programación de C#)
La conversión boxing solo se aplica a los objetos basados en tipos que aceptan valores NULL si el valor del objeto no es NULL. Si <xref:System.Nullable%601.HasValue%2A> es `false`, la referencia de objeto se asigna a `null` en lugar de aplicar la conversión boxing. Por ejemplo:  
  
```csharp  
bool? b = null;  
object o = b;  
// Now o is null.  
```  
  
 Si el objeto no es NULL (si <xref:System.Nullable%601.HasValue%2A> es `true`), tiene lugar la conversión boxing, pero solo se aplica al tipo subyacente en el que se basa el objeto que acepta valores NULL. La conversión boxing de un tipo de valor no NULL que acepta valores NULL se aplica al propio tipo de valor, no al objeto <xref:System.Nullable%601?displayProperty=fullName> que ajusta el tipo de valor. Por ejemplo:  
  
```csharp  
bool? b = false;  
int? i = 44;  
object bBoxed = b; // bBoxed contains a boxed bool.  
object iBoxed = i; // iBoxed contains a boxed int.  
```  
  
 Los dos objetos a los que se aplica la conversión boxing son idénticos a aquellos creados aplicando la conversión boxing a tipos que no aceptan valores NULL. Además, al igual que los tipos sin conversión boxing que aceptan valores NULL, se les puede aplicar la conversión unboxing en los tipos que aceptan valores NULL, como en el ejemplo siguiente:  
  
```csharp  
bool? b2 = (bool?)bBoxed;  
int? i2 = (int?)iBoxed;  
```  
  
## <a name="remarks"></a>Comentarios  
 El comportamiento de los tipos que aceptan valores NULL cuando se aplica la conversión boxing proporciona dos ventajas:  
  
1.  Se comprueba si los objetos que aceptan valores NULL y sus homólogos a los que se aplica la conversión boxing tienen valores NULL:  
  
    ```csharp  
    bool? b = null;  
    object boxedB = b;  
    if (b == null)  
    {  
      // True.  
    }  
    if (boxedB == null)  
    {  
      // Also true.  
    }  
    ```  
  
2.  Los tipos que aceptan valores NULL y a los que se aplica la conversión boxing admiten la función del tipo subyacente:  
  
    ```csharp  
    double? d = 44.4;  
    object iBoxed = d;  
    // Access IConvertible interface implemented by double.  
    IConvertible ic = (IConvertible)iBoxed;  
    int i = ic.ToInt32(null);  
    string str = ic.ToString();  
    ```  
  
## <a name="see-also"></a>Vea también  
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)   
 [Tipos que aceptan valores NULL](../../../csharp/programming-guide/nullable-types/index.md)   
 [Cómo: Identificar tipos que aceptan valores NULL](../../../csharp/programming-guide/nullable-types/how-to-identify-a-nullable-type.md)

