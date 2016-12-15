---
title: "El espacio de nombres o tipo especificado en las importaciones &#39;&lt;nombreCompletoDeElemento&gt;&#39; no contiene miembros p&#250;blicos o no se encuentra | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "bc40056"
  - "vbc40056"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC40056"
ms.assetid: b59f5754-444f-4378-9272-9678b437e84a
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# El espacio de nombres o tipo especificado en las importaciones &#39;&lt;nombreCompletoDeElemento&gt;&#39; no contiene miembros p&#250;blicos o no se encuentra
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

El espacio de nombres o el tipo especificado en las importaciones '\<nombreCompletoDeElemento\>' no contienen ningún miembro público o no se encuentran.Asegúrese de que el espacio de nombres o el tipo se hayan definido y de que contengan al menos un miembro público.Asegúrese de que el nombre de alias no contiene otros alias.  
  
 Una instrucción `Imports` especifica un elemento contenedor que no se puede encontrar o que no define ningún miembro `Public`.  
  
 Un *elemento contenedor* puede ser un espacio de nombres, una clase, una estructura, un módulo, una interfaz o una enumeración.  El elemento contenedor incluye miembros, como variables, procedimientos u otros elementos contenedores.  
  
 El propósito de importar es permitir que su código obtenga acceso a los miembros del espacio de nombres o del tipo sin tener que calificarlos.  Quizás el proyecto también necesite agregar una referencia al espacio de nombres o tipo.  Para obtener más información, vea "Importar elementos contenedores" en [Referencias a elementos declarados](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).  
  
 Si el compilador no puede encontrar el elemento contenedor especificado, no podrá resolver las referencias que lo utilizan.  Si encuentra el elemento pero éste no expone ningún miembro `Public`, no se realizará correctamente ninguna referencia.  En ambos casos carece de sentido importar el elemento.  
  
 Tenga presente que si importa un elemento contenedor y le asigna un alias de importación, no podrá utilizar ese alias de importación para importar ningún otro elemento.  En el siguiente código se genera un error de compilación.  
  
 `Imports`   `winfrm`   `= System.Windows.Forms`  
  
 `' The following statement is`   `INVALID`   `because it reuses an import alias.`  
  
 `Imports behav =`   `winfrm`  `.Design.Behavior`  
  
 **Identificador de error:** BC40056  
  
### Para corregir este error  
  
1.  Compruebe que puede obtener acceso desde su proyecto al elemento contenedor.  
  
2.  Compruebe que la especificación del elemento contenedor no incluye ningún alias de importación que provenga de otra importación.  
  
3.  Compruebe que el elemento contenedor expone por lo menos un miembro `Public`.  
  
## Vea también  
 [Instrucción Imports \(Tipo y espacio de nombres de .NET\)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)   
 [Namespace \(Instrucción\)](../../../visual-basic/language-reference/statements/namespace-statement.md)   
 [Public](../../../visual-basic/language-reference/modifiers/public.md)   
 [Espacios de nombres en Visual Basic](../../../visual-basic/programming-guide/program-structure/namespaces.md)   
 [Referencias a elementos declarados](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)