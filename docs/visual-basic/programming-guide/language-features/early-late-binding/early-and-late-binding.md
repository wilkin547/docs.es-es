---
title: "Enlace en tiempo de compilaci&#243;n y en tiempo de ejecuci&#243;n (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "enlace, tardío y temprano"
  - "enlace temprano"
  - "enlace temprano, compilador de Visual Basic"
  - "enlace tardío"
  - "enlace tardío, compilador de Visual Basic"
  - "objetos [Visual Basic], enlazados tempranamente"
  - "objetos [Visual Basic], enlazados tempranamente"
  - "objetos [Visual Basic], enlazados tardíamente"
  - "objetos [Visual Basic], enlazados tardíamente"
  - "compilador de Visual Basic, enlace temprano y tardío"
ms.assetid: d6ff7f1e-b94f-4205-ab8d-5cfa91758724
caps.latest.revision: 10
caps.handback.revision: 10
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Enlace en tiempo de compilaci&#243;n y en tiempo de ejecuci&#243;n (Visual Basic)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

El compilador de [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] lleva a cabo un proceso denominado `binding` cuando se asigna un objeto a una variable de objeto.  Un objeto es de *enlace en tiempo de compilación* cuando se asigna a una variable que se declara de un tipo de objeto específico.  Los objetos de enlace en tiempo de compilación permiten al compilador asignar memoria y realizar otras optimizaciones antes de que se ejecute la aplicación.  Por ejemplo, en el siguiente fragmento de código se declara que una variable es de tipo <xref:System.IO.FileStream>:  
  
 [!code-vb[VbVbalrOOP#90](../../../../visual-basic/misc/codesnippet/VisualBasic/early-and-late-binding_1.vb)]  
  
 Como <xref:System.IO.FileStream> es un tipo de objeto específico, la instancia asignada a `FS` es de enlace en tiempo de compilación.  
  
 Por el contrario, un objeto es de *enlace en tiempo de ejecución* cuando se asigna a una variable que se declara de tipo `Object`.  Los objetos de este tipo pueden contener referencias a cualquier objeto, pero carecen de muchas de las ventajas de los objetos de enlace en tiempo de compilación.  Por ejemplo, en el siguiente fragmento de código se declara una variable de objeto para contener un objeto devuelto por la función `CreateObject`:  
  
 [!code-vb[VbVbalrOOP#91](../../../../visual-basic/misc/codesnippet/VisualBasic/early-and-late-binding_2.vb)]  
  
## Ventajas del enlace en tiempo de compilación  
 Siempre que sea posible, utilice objetos de enlace en tiempo de compilación, puesto que permiten al compilador realizar importantes optimizaciones que producen aplicaciones más eficientes.  Los objetos de enlace en tiempo de compilación son bastante más rápidos y también facilitan la lectura y el mantenimiento del código, ya que declaran exactamente qué clase de objetos se están utilizando.  Otra ventaja del enlace en tiempo de compilación consiste en que permite el uso de características útiles como la finalización automática de código y la Ayuda dinámica, puesto que el entorno de desarrollo integrado \(IDE\) de [!INCLUDE[vsprvs](../../../../csharp/includes/vsprvs_md.md)] puede determinar exactamente el tipo de objeto con el que se está trabajando mientras se edita el código.  El enlace en tiempo de compilación reduce el número y la gravedad de los errores en tiempo de ejecución al permitir que el compilador notifique los errores cuando se compila un programa.  
  
> [!NOTE]
>  El enlace en tiempo de ejecución sólo puede utilizarse para obtener acceso a miembros de tipo declarados como `Public`.  Tener acceso a miembros declarados como `Friend` o `Protected Friend` produce un error en tiempo de ejecución.  
  
## Vea también  
 <xref:Microsoft.VisualBasic.Interaction.CreateObject%2A>   
 [Duración de los objetos: cómo se crean y destruyen](../../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md)   
 [Object \(Tipo de datos\)](../../../../visual-basic/language-reference/data-types/object-data-type.md)