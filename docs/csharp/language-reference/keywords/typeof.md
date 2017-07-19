---
title: typeof (Referencia de C#) | Microsoft Docs
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- typeof
- typeof_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- typeof keyword [C#]
ms.assetid: 0c08d880-515e-46bb-8cd2-48b8dd62c08d
caps.latest.revision: 21
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
ms.translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 0590aa8a339dc58b7215722a530a71f8973864d4
ms.contentlocale: es-es
ms.lasthandoff: 03/13/2017

---
# <a name="typeof-c-reference"></a>typeof (Referencia de C#)
Se usa para obtener el objeto `System.Type` de un tipo. Una expresión `typeof` tiene el formato siguiente:  
  
```  
System.Type type = typeof(int);  
```  
  
## <a name="remarks"></a>Comentarios  
 Para obtener el tipo en tiempo de ejecución de una expresión, puede usar el método <xref:System.Object.GetType%2A> de .NET Framework, como en el ejemplo siguiente:  
  
```  
int i = 0;  
System.Type type = i.GetType();  
```  
  
 El operador `typeof` no se puede sobrecargar.  
  
 El operador `typeof` también puede usarse en tipos genéricos abiertos. Los tipos con más de un parámetro de tipo deben incluir el número correspondiente de comas en la especificación. En el ejemplo siguiente se muestra cómo determinar si el tipo de valor devuelto de un método es un <xref:System.Collections.Generic.IEnumerable%601> genérico. Suponga que el método es una instancia de un tipo de MethodInfo:  
  
```  
string s = method.ReturnType.GetInterface  
    (typeof(System.Collections.Generic.IEnumerable<>).FullName);  
```  
  
## <a name="example"></a>Ejemplo  
 [!code-cs[csrefKeywordsOperator#12](../../../csharp/language-reference/keywords/codesnippet/CSharp/typeof_1.cs)]  
  
## <a name="example"></a>Ejemplo  
 En este ejemplo se usa el método <xref:System.Object.GetType%2A> para determinar el tipo que se emplea para contener el resultado de un cálculo numérico. Esto varía en función de los requisitos de almacenamiento del número resultante.  
  
 [!code-cs[csrefKeywordsOperator#13](../../../csharp/language-reference/keywords/codesnippet/CSharp/typeof_2.cs)]  
  
## <a name="c-language-specification"></a>Especificación del lenguaje C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Type?displayProperty=fullName>   
 [Referencia de C#](../../../csharp/language-reference/index.md)   
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)   
 [Palabras clave de C#](../../../csharp/language-reference/keywords/index.md)   
 [is](../../../csharp/language-reference/keywords/is.md)   
 [Palabras clave de operador](../../../csharp/language-reference/keywords/operator-keywords.md)
