---
description: 'Más información sobre: Cómo: crear un método de extensión Add usado por un inicializador de colección (Visual Basic)'
title: Procedimiento para crear un método de extensión de adiciones usado por un inicializador de colección
ms.date: 07/20/2015
helpviewer_keywords:
- collection initializers [Visual Basic]
ms.assetid: f64b52c7-8b11-4410-93a6-cb3aeebcc772
ms.openlocfilehash: 1fbe6f438c4761ae668a6bd6a0a2c38c8efdb439
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100475479"
---
# <a name="how-to-create-an-add-extension-method-used-by-a-collection-initializer-visual-basic"></a>Cómo: Crear un método de extensión Add usado por un inicializador de colección (Visual Basic)

Cuando se usa un inicializador de colección para crear una colección, el compilador Visual Basic busca un `Add` método del tipo de colección para el que los parámetros del `Add` método coinciden con los tipos de los valores del inicializador de colección. Este `Add` método se usa para rellenar la colección con los valores del inicializador de colección.  
  
 Si no `Add` existe ningún método coincidente y no se puede modificar el código de la colección, puede Agregar un método de extensión denominado `Add` que toma los parámetros necesarios para el inicializador de colección. Normalmente, esto es lo que debe hacer cuando se usan inicializadores de colección para colecciones genéricas.  
  
## <a name="example"></a>Ejemplo  

 En el ejemplo siguiente se muestra cómo agregar un método de extensión al <xref:System.Collections.Generic.List%601> tipo genérico para que se pueda utilizar un inicializador de colección para agregar objetos de tipo `Employee` . El método de extensión le permite usar la sintaxis de inicializador de colección abreviada.  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo1#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCollectionInitializersHowTo1/VB/Module1.vb#1)]  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo1#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCollectionInitializersHowTo1/VB/Module1.vb#2)]  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo1#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCollectionInitializersHowTo1/VB/Module1.vb#3)]  
  
## <a name="see-also"></a>Consulte también

- [Inicializadores de colección](index.md)
- [Procedimiento para crear una colección usada por un inicializador de colección](how-to-create-a-collection-used-by-a-collection-initializer.md)
