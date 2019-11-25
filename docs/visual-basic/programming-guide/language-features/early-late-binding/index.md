---
title: Enlace en tiempo de compilación y en tiempo de ejecución
ms.date: 07/20/2015
helpviewer_keywords:
- early binding [Visual Basic]
- objects [Visual Basic], late-bound
- objects [Visual Basic], early-bound
- objects [Visual Basic], late bound
- early binding [Visual Basic], Visual Basic compiler
- binding [Visual Basic], late and early
- objects [Visual Basic], early bound
- Visual Basic compiler, early and late binding
- late binding [Visual Basic]
- late binding [Visual Basic], Visual Basic compiler
ms.assetid: d6ff7f1e-b94f-4205-ab8d-5cfa91758724
ms.openlocfilehash: bd70d8642c18e9bc2baba8128ec908c88e0477ce
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74345185"
---
# <a name="early-and-late-binding-visual-basic"></a>Enlace en tiempo de compilación y en tiempo de ejecución (Visual Basic)
The Visual Basic compiler performs a process called `binding` when an object is assigned to an object variable. Un objeto se *enlaza de manera anticipada* cuando se asigna a una variable que se declara de un tipo de objeto específico. Los objetos enlazados de manera anticipada permiten al compilador asignar memoria y realizar otras optimizaciones antes de que se ejecute la aplicación. Por ejemplo, el fragmento de código siguiente declara que una variable es de tipo <xref:System.IO.FileStream>:  
  
 [!code-vb[VbVbalrOOP#90](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#90)]  
  
 Como <xref:System.IO.FileStream> es un tipo de objeto específico, la instancia asignada a `FS` se enlaza de manera anticipada.  
  
 Por el contrario, un objeto se *enlaza en tiempo de ejecución* cuando se asigna a una variable que se declara como variable de tipo `Object`. Los objetos de este tipo pueden contener referencias a cualquier objeto, pero carecen de muchas de las ventajas de los objetos con enlaces anticipados. Por ejemplo, el fragmento de código siguiente declara una variable de objeto para contener un objeto devuelto por la función `CreateObject`:  
  
 [!code-vb[VbVbalrOOP#91](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/LateBinding.vb#91)]  
  
## <a name="advantages-of-early-binding"></a>Ventajas del enlace anticipado  
 Debe utilizar objetos con enlace anticipado siempre que sea posible, ya que permiten al compilador realizar importantes optimizaciones que producen aplicaciones más eficientes. Los objetos con enlace anticipado son considerablemente más rápidos que los objetos con enlace en tiempo de ejecución y permiten que el código sea más fácil de leer y mantener, ya que declaran exactamente qué clase de objetos se están utilizando. Another advantage to early binding is that it enables useful features such as automatic code completion and Dynamic Help because the Visual Studio integrated development environment (IDE) can determine exactly what type of object you are working with as you edit the code. El enlace anticipado reduce el número y la gravedad de los errores en tiempo de ejecución porque permite que el compilador notifique errores cuando se compila un programa.  
  
> [!NOTE]
> El enlace en tiempo de ejecución solo puede utilizarse para acceder a miembros de tipo declarados como `Public`. El acceso a miembros declarados como `Friend` o `Protected Friend` produce un error en tiempo de ejecución.  
  
## <a name="see-also"></a>Vea también

- <xref:Microsoft.VisualBasic.Interaction.CreateObject%2A>
- [Duración de los objetos: cómo se crean y destruyen](../../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md)
- [Tipo de objeto de datos](../../../../visual-basic/language-reference/data-types/object-data-type.md)
