---
title: Enlace en tiempo de compilación y en tiempo de ejecución (Visual Basic)
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
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
caps.latest.revision: 10
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 10ecc965fb6d728454b3af33a6e93b2d7dbc327d
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/26/2018
---
# <a name="early-and-late-binding-visual-basic"></a>Enlace en tiempo de compilación y en tiempo de ejecución (Visual Basic)
El compilador de Visual Basic ejecuta un proceso denominado `binding` cuando se asigna un objeto a una variable de objeto. Un objeto se *enlaza de manera anticipada* cuando se asigna a una variable que se declara de un tipo de objeto específico. Los objetos enlazados de manera anticipada permiten al compilador asignar memoria y realizar otras optimizaciones antes de que se ejecute la aplicación. Por ejemplo, el fragmento de código siguiente declara que una variable es de tipo <xref:System.IO.FileStream>:  
  
 [!code-vb[VbVbalrOOP#90](../../../../visual-basic/misc/codesnippet/VisualBasic/early-and-late-binding_1.vb)]  
  
 Como <xref:System.IO.FileStream> es un tipo de objeto específico, la instancia asignada a `FS` se enlaza de manera anticipada.  
  
 Por el contrario, un objeto se *enlaza en tiempo de ejecución* cuando se asigna a una variable que se declara como variable de tipo `Object`. Los objetos de este tipo pueden contener referencias a cualquier objeto, pero carecen de muchas de las ventajas de los objetos con enlaces anticipados. Por ejemplo, el fragmento de código siguiente declara una variable de objeto para contener un objeto devuelto por la función `CreateObject`:  
  
 [!code-vb[VbVbalrOOP#91](../../../../visual-basic/misc/codesnippet/VisualBasic/early-and-late-binding_2.vb)]  
  
## <a name="advantages-of-early-binding"></a>Ventajas del enlace anticipado  
 Debe utilizar objetos con enlace anticipado siempre que sea posible, ya que permiten al compilador realizar importantes optimizaciones que producen aplicaciones más eficientes. Los objetos con enlace anticipado son considerablemente más rápidos que los objetos con enlace en tiempo de ejecución y permiten que el código sea más fácil de leer y mantener, ya que declaran exactamente qué clase de objetos se están utilizando. Otra ventaja del enlace anticipado es que habilita características útiles como la finalización automática de código y la Ayuda dinámica, porque el entorno de desarrollo integrado (IDE) de [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] puede determinar exactamente con qué tipo de objeto está trabajando mientras se edita el código. El enlace anticipado reduce el número y la gravedad de los errores en tiempo de ejecución porque permite que el compilador notifique errores cuando se compila un programa.  
  
> [!NOTE]
>  El enlace en tiempo de ejecución solo puede utilizarse para acceder a miembros de tipo declarados como `Public`. El acceso a miembros declarados como `Friend` o `Protected Friend` produce un error en tiempo de ejecución.  
  
## <a name="see-also"></a>Vea también  
 <xref:Microsoft.VisualBasic.Interaction.CreateObject%2A>  
 [Duración de los objetos: cómo se crean y destruyen](../../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md)  
 [Tipo de objeto de datos](../../../../visual-basic/language-reference/data-types/object-data-type.md)
