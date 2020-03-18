---
title: 'Procedimiento Controlar una excepción mediante Try y Catch: Guía de programación de C#'
ms.date: 07/20/2015
helpviewer_keywords:
- exception handling [C#], try/catch blocks
- exceptions [C#], try/catch blocks
- try/catch blocks [C#]
ms.assetid: ca8e3773-980e-4767-8633-7408540e9818
ms.openlocfilehash: adfc53cbe4fd603ac3a6de6b9a0162320d5a2e19
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "75712291"
---
# <a name="how-to-handle-an-exception-using-trycatch-c-programming-guide"></a>Procedimiento Controlar una excepción mediante Try y Catch (Guía de programación de C#)
El propósito de un bloque [try-catch](../../language-reference/keywords/try-catch.md) es detectar y controlar una excepción generada por código en funcionamiento. Algunas excepciones se pueden controlar en un bloque `catch` y es posible resolver el problema sin que se vuelva a producir la excepción, pero la mayoría de las veces lo único que se puede hacer es asegurarse de que se produzca la excepción adecuada.  
  
## <a name="example"></a>Ejemplo  
 En este ejemplo, <xref:System.IndexOutOfRangeException> no es la excepción más adecuada. Tiene más sentido la excepción <xref:System.ArgumentOutOfRangeException> para el método, ya que el error lo provoca el argumento `index` pasado por el autor de la llamada.  
  
 [!code-csharp[csProgGuideExceptions#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideExceptions/CS/Exceptions.cs#5)]  
  
## <a name="comments"></a>Comentarios  
 El código que produce una excepción está incluido en el bloque `try`. Se agrega una instrucción `catch` inmediatamente después para controlar `IndexOutOfRangeException`, si se produce. El bloque `catch` controla la excepción `IndexOutOfRangeException` y produce en su lugar la excepción `ArgumentOutOfRangeException`, más adecuada. Para proporcionar al autor de la llamada tanta información como sea posible, considere la posibilidad de especificar la excepción original como <xref:System.Exception.InnerException%2A> de la nueva excepción. Dado que la propiedad <xref:System.Exception.InnerException%2A> es [readonly](../../language-reference/keywords/readonly.md), debe asignarla en el constructor de la nueva excepción.  
  
## <a name="see-also"></a>Vea también

- [Guía de programación de C#](../index.md)
- [Excepciones y control de excepciones](./index.md)
- [Control de excepciones](./exception-handling.md)
