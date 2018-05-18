---
title: typeof (Referencia de C#)
ms.date: 07/20/2015
f1_keywords:
- typeof
- typeof_CSharpKeyword
helpviewer_keywords:
- typeof keyword [C#]
ms.assetid: 0c08d880-515e-46bb-8cd2-48b8dd62c08d
ms.openlocfilehash: be79fa4f2cfb1119a50201bf6c18a144726f2f21
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
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
 [!code-csharp[csrefKeywordsOperator#12](../../../csharp/language-reference/keywords/codesnippet/CSharp/typeof_1.cs)]  
  
## <a name="example"></a>Ejemplo  
 En este ejemplo se usa el método <xref:System.Object.GetType%2A> para determinar el tipo que se usa para contener el resultado de un cálculo numérico. Esto varía en función de los requisitos de almacenamiento del número resultante.  
  
 [!code-csharp[csrefKeywordsOperator#13](../../../csharp/language-reference/keywords/codesnippet/CSharp/typeof_2.cs)]  
  
## <a name="c-language-specification"></a>Especificación del lenguaje C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Type?displayProperty=nameWithType>  
 [Referencia de C#](../../../csharp/language-reference/index.md)  
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)  
 [Palabras clave de C#](../../../csharp/language-reference/keywords/index.md)  
 [is](../../../csharp/language-reference/keywords/is.md)  
 [Palabras clave de operador](../../../csharp/language-reference/keywords/operator-keywords.md)
