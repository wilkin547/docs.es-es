---
title: Operador TryCast
ms.date: 07/20/2015
f1_keywords:
- vb.trycast
- trycast
helpviewer_keywords:
- TryCast keyword [Visual Basic]
ms.assetid: d1ef5d47-fef4-491e-b014-1d910628f65c
ms.openlocfilehash: dc4807781f9e1aaf894016952911bd7b32c42948
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "90875313"
---
# <a name="trycast-operator-visual-basic"></a>TryCast (Operador) (Visual Basic)

Introduce una operación de conversión de tipos que no produce una excepción.  
  
## <a name="remarks"></a>Comentarios  

 Si se produce un error en una conversión intentada `CType` y `DirectCast` ambos producen un <xref:System.InvalidCastException> error. Esto puede afectar negativamente al rendimiento de la aplicación. `TryCast` no devuelve [nada](../nothing.md), de modo que, en lugar de tener que controlar una posible excepción, solo se necesita probar el resultado devuelto con `Nothing` .  
  
 La `TryCast` palabra clave se usa de la misma manera que se usa la [función ctype](../functions/ctype-function.md) y la palabra clave del [operador DirectCast](directcast-operator.md) . Proporcione una expresión como primer argumento y un tipo al que convertirlo como segundo argumento. `TryCast` solo funciona en tipos de referencia, como clases e interfaces. Requiere una relación de herencia o implementación entre los dos tipos. Esto significa que un tipo debe heredar de o implementar el otro.  
  
## <a name="errors-and-failures"></a>Errores y errores  

 `TryCast` genera un error del compilador si detecta que no existe ninguna relación de herencia o de implementación. Pero la falta de un error del compilador no garantiza una conversión correcta. Si la conversión deseada es de restricción, podría producirse un error en tiempo de ejecución. Si esto ocurre, no `TryCast` devuelve [nada](../nothing.md).  
  
## <a name="conversion-keywords"></a>Palabras clave para conversiones  

 A continuación se muestra una comparación de las palabras clave de conversión de tipos.  
  
|Palabra clave|Tipos de datos|Relación entre argumentos|Error en tiempo de ejecución|  
|---|---|---|---|  
|[CType Function](../functions/ctype-function.md)|Cualquier tipo de datos|La conversión de ampliación o de restricción debe definirse entre los dos tipos de datos|Produce <xref:System.InvalidCastException>|  
|[Operador DirectCast](directcast-operator.md)|Cualquier tipo de datos|Un tipo debe heredar de o implementar el otro tipo|Produce <xref:System.InvalidCastException>|  
|`TryCast`|Solo tipos de referencia|Un tipo debe heredar de o implementar el otro tipo|No devuelve [nada](../nothing.md)|  
  
## <a name="example"></a>Ejemplo  

 En el ejemplo siguiente se muestra cómo utilizar `TryCast`.  
  
 [!code-vb[VbVbalrKeywords#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class1.vb#6)]  
  
## <a name="see-also"></a>Consulte también

- [Widening and Narrowing Conversions](../../programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
- [Conversiones implícitas y explícitas](../../programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
