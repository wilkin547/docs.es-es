---
title: 'Cómo: Controlar una excepción mediante Try y Catch (Guía de programación de C#)'
ms.date: 07/20/2015
helpviewer_keywords:
- exception handling [C#], try/catch blocks
- exceptions [C#], try/catch blocks
- try/catch blocks [C#]
ms.assetid: ca8e3773-980e-4767-8633-7408540e9818
ms.openlocfilehash: b67a3d7b6d2e10519363a273b7dd1d8b61317d1c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33338076"
---
# <a name="how-to-handle-an-exception-using-trycatch-c-programming-guide"></a>Cómo: Controlar una excepción mediante Try y Catch (Guía de programación de C#)
El propósito de un bloque [try-catch](../../../csharp/language-reference/keywords/try-catch.md) es detectar y controlar una excepción generada por código en funcionamiento. Algunas excepciones se pueden controlar en un bloque `catch` y es posible resolver el problema sin que se vuelva a producir la excepción, pero la mayoría de las veces lo único que se puede hacer es asegurarse de que se produzca la excepción adecuada.  
  
## <a name="example"></a>Ejemplo  
 En este ejemplo, <xref:System.IndexOutOfRangeException> no es la excepción más adecuada. Tiene más sentido la excepción <xref:System.ArgumentOutOfRangeException> para el método, ya que el error lo provoca el argumento `index` pasado por el autor de la llamada.  
  
 [!code-csharp[csProgGuideExceptions#5](../../../csharp/programming-guide/exceptions/codesnippet/CSharp/how-to-handle-an-exception-using-try-catch_1.cs)]  
  
## <a name="comments"></a>Comentarios  
 El código que produce una excepción está incluido en el bloque `try`. Se agrega una instrucción `catch` inmediatamente después para controlar `IndexOutOfRangeException`, si se produce. El bloque `catch` controla la excepción `IndexOutOfRangeException` y produce en su lugar la excepción `ArgumentOutOfRangeException`, más adecuada. Para proporcionar al autor de la llamada tanta información como sea posible, considere la posibilidad de especificar la excepción original como <xref:System.Exception.InnerException%2A> de la nueva excepción. Dado que la propiedad <xref:System.Exception.InnerException%2A> es [readonly](../../../csharp/language-reference/keywords/readonly.md), debe asignarla en el constructor de la nueva excepción.  
  
## <a name="see-also"></a>Vea también  
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)  
 [Excepciones y control de excepciones](../../../csharp/programming-guide/exceptions/index.md)  
 [Control de excepciones](../../../csharp/programming-guide/exceptions/exception-handling.md)
