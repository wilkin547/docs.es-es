---
title: "El espacio de nombres o tipo especificado en las importaciones del proyecto &#39;&lt;nombreCompletoDeElemento&gt;&#39; no tiene miembros p&#250;blicos o no se encuentra | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vbc40057"
  - "bc40057"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC40057"
ms.assetid: 4ae3506e-2ebe-4ff3-995d-14ac60db5e9f
caps.latest.revision: 10
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 10
---
# El espacio de nombres o tipo especificado en las importaciones del proyecto &#39;&lt;nombreCompletoDeElemento&gt;&#39; no tiene miembros p&#250;blicos o no se encuentra
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

El espacio de nombres o tipo especificado en las importaciones de nivel de proyecto '\<nombreCompletoDeElemento\>' no contienen ningún miembro público o no se encuentran.Asegúrese de que el espacio de nombres o el tipo se hayan definido y de que contengan al menos un miembro público.Asegúrese de que el nombre de alias no contiene otros alias.  
  
 Una propiedad de importación de un proyecto especifica un elemento contenedor que no se puede encontrar o no define ningún miembro `Public`.  
  
 Un *elemento contenedor* puede ser un espacio de nombres, una clase, una estructura, un módulo, una interfaz o una enumeración.  El elemento contenedor incluye miembros, como variables, procedimientos u otros elementos contenedores.  
  
 El propósito de importar es permitir que su código obtenga acceso a los miembros del espacio de nombres o del tipo sin tener que calificarlos.  Quizás el proyecto también necesite agregar una referencia al espacio de nombres o tipo.  Para obtener más información, vea "Importar elementos contenedores" en [Referencias a elementos declarados](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).  
  
 Si el compilador no puede encontrar el elemento contenedor especificado, no podrá resolver las referencias que lo utilizan.  Si encuentra el elemento pero éste no expone ningún miembro `Public`, no se realizará correctamente ninguna referencia.  En ambos casos carece de sentido importar el elemento.  
  
 Para especificar los elementos que se van a importar se utiliza el **Diseñador de proyectos**.  Utilice la sección **Espacios de nombres importados** de la página **Referencias**.  Puede llegar al **Diseñador de proyectos** haciendo doble clic en el icono **Mi proyecto** del **Explorador de soluciones**.  
  
 **Identificador de error:** BC40057  
  
### Para corregir este error  
  
1.  Abra el **Diseñador de proyectos** y cambie a la página **Referencia**.  
  
2.  En la sección **Espacios de nombres importados**, compruebe que desde su proyecto se puede obtener acceso al elemento contenedor.  
  
3.  Compruebe que el elemento contenedor expone por lo menos un miembro `Public`.  
  
## Vea también  
 [Página Referencias, Diseñador de proyectos \(Visual Basic\)](/visual-studio/ide/reference/references-page-project-designer-visual-basic)   
 [Cómo: Modificar las propiedades y los valores de configuración del proyecto](http://msdn.microsoft.com/es-es/e7184bc5-2f2b-4b4f-aa9a-3ecfcbc48b67)   
 [Public](../../../visual-basic/language-reference/modifiers/public.md)   
 [Espacios de nombres en Visual Basic](../../../visual-basic/programming-guide/program-structure/namespaces.md)   
 [Referencias a elementos declarados](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)