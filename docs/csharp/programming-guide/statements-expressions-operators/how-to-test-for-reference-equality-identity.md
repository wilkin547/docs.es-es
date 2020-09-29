---
title: 'Procedimiento Probar la igualdad de referencias (identidad): Guía de programación de C#'
description: Aprenda a probar la igualdad de referencia (Identidad). Vea un ejemplo de código y examine los recursos adicionales disponibles.
ms.date: 07/20/2015
helpviewer_keywords:
- object identity [C#]
- reference equality [C#]
ms.assetid: 91307fda-267b-4fd2-a338-2aada39ee791
ms.openlocfilehash: 1d1a0e5d80ac8d2a689e75acbc6099b92e16f23f
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91151446"
---
# <a name="how-to-test-for-reference-equality-identity-c-programming-guide"></a>Procedimiento Probar la igualdad de referencias (identidad) (Guía de programación de C#)

No tiene que implementar ninguna lógica personalizada para admitir las comparaciones de igualdad de referencias en los tipos. Esta funcionalidad se proporciona para todos los tipos mediante el método <xref:System.Object.ReferenceEquals%2A?displayProperty=nameWithType> estático.  
  
 En el ejemplo siguiente, se muestra cómo determinar si dos variables tienen *igualdad de referencia*, lo que significa que hacen referencia al mismo objeto en la memoria.  
  
 En el ejemplo también se muestra por qué <xref:System.Object.ReferenceEquals%2A?displayProperty=nameWithType> siempre devuelve `false` para los tipos de valor y por qué no se debe usar <xref:System.Object.ReferenceEquals%2A> para determinar la igualdad entre cadenas.  
  
## <a name="example"></a>Ejemplo  

 [!code-csharp[csProgGuideObjects#90](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#90)]  
  
 La implementación de `Equals` en la clase base universal <xref:System.Object?displayProperty=nameWithType> también realiza una comprobación de la igualdad de referencias; sin embargo, es mejor no seguir este procedimiento porque, en el caso de que una clase invalide el método, los resultados podrían no ser los esperados. Lo mismo se cumple para los operadores `==` y `!=`. Cuando se usan en tipos de referencia, el comportamiento predeterminado de `==` y `!=` consiste en realizar una comprobación de la igualdad de referencias. Sin embargo, las clases derivadas pueden sobrecargar el operador para realizar una comprobación de la igualdad de valores. Para minimizar las posibilidades de error, lo mejor es usar siempre <xref:System.Object.ReferenceEquals%2A> cuando deba determinarse si dos objetos tienen igualdad de referencia.  
  
 El runtime siempre aplica el método Intern a las cadenas constantes dentro del mismo ensamblado. Es decir, solo se conserva una instancia de cada cadena literal única. Sin embargo, el runtime no garantiza que se vaya a aplicar el método Intern a las cadenas creadas en tiempo de ejecución, ni tampoco que dicho método se aplique a dos cadenas constantes iguales en distintos ensamblados.  
  
## <a name="see-also"></a>Consulte también

- [Comparaciones de igualdad](./equality-comparisons.md)
