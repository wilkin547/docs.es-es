---
title: params (Referencia de C#)
ms.date: 07/20/2015
f1_keywords:
- params_CSharpKeyword
- params
helpviewer_keywords:
- parameters [C#], params
- params keyword [C#]
ms.assetid: 1690815e-b52b-4967-8380-5780aff08012
ms.openlocfilehash: 692c2f61ae99f1c1c8e04a5a1bcad08814d286fe
ms.sourcegitcommit: a1e35d4e94edab384a63406c0a5438306873031b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/21/2018
ms.locfileid: "42752036"
---
# <a name="params-c-reference"></a>params (Referencia de C#)
Mediante el uso de la palabra clave `params`, puede especificar un [parámetro de método](../../../csharp/language-reference/keywords/method-parameters.md) que toma un número variable de argumentos.  
  
 Puede enviar una lista separada por comas de argumentos del tipo especificado en la declaración de parámetro o una matriz de argumentos del tipo especificado. También puede no enviar ningún argumento. Si no envía ningún argumento, la longitud de la lista `params` es cero.  
  
 No se permiten parámetros adicionales después de la palabra clave `params` en una declaración de método, y solo se permite una palabra clave `params` en una declaración de método.  
 
 El tipo declarado del parámetro `params` debe ser una matriz unidimensional, como se muestra en el ejemplo siguiente. En caso contrario, se produce un error del compilador [CS0225](../../../csharp/misc/cs0225.md).
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestran varias maneras de enviar argumentos a un parámetro `params`.  
  
 [!code-csharp[csrefKeywordsMethodParams#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/params_1.cs)]  
  
## <a name="c-language-specification"></a>Especificación del lenguaje C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [Referencia de C#](../../../csharp/language-reference/index.md)  
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)  
 [Palabras clave de C#](../../../csharp/language-reference/keywords/index.md)  
 [Parámetros de métodos](../../../csharp/language-reference/keywords/method-parameters.md)
