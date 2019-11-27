---
title: 'Cómo: Crear un método de extensión Add usado por un inicializador de colección'
ms.date: 07/20/2015
helpviewer_keywords:
- collection initializers [Visual Basic]
ms.assetid: f64b52c7-8b11-4410-93a6-cb3aeebcc772
ms.openlocfilehash: 6d5f9d38b413b79f111a14ec3829c57a9797ce54
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74346722"
---
# <a name="how-to-create-an-add-extension-method-used-by-a-collection-initializer-visual-basic"></a>Cómo: Crear un método de extensión Add usado por un inicializador de colección (Visual Basic)
Cuando se usa un inicializador de colección para crear una colección, el compilador Visual Basic busca un método `Add` del tipo de colección para el que los parámetros del método `Add` coinciden con los tipos de los valores del inicializador de colección. Este método `Add` se usa para rellenar la colección con los valores del inicializador de colección.  
  
 Si no existe ningún método de `Add` coincidente y no se puede modificar el código de la colección, puede Agregar un método de extensión denominado `Add` que toma los parámetros necesarios para el inicializador de colección. Normalmente, esto es lo que debe hacer cuando se usan inicializadores de colección para colecciones genéricas.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo agregar un método de extensión al tipo de <xref:System.Collections.Generic.List%601> genérico para que se pueda utilizar un inicializador de colección para agregar objetos de tipo `Employee`. El método de extensión le permite usar la sintaxis de inicializador de colección abreviada.  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo1#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCollectionInitializersHowTo1/VB/Module1.vb#1)]  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo1#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCollectionInitializersHowTo1/VB/Module1.vb#2)]  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo1#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCollectionInitializersHowTo1/VB/Module1.vb#3)]  
  
## <a name="see-also"></a>Vea también

- [Inicializadores de colección](../../../../visual-basic/programming-guide/language-features/collection-initializers/index.md)
- [Crear una colección usada por un inicializador de colección](../../../../visual-basic/programming-guide/language-features/collection-initializers/how-to-create-a-collection-used-by-a-collection-initializer.md)
