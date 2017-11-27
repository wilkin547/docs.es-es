---
title: "&lt;mensaje&gt; este error también podría ser debido a la combinación de una referencia de archivo con una referencia de proyecto al ensamblado &#39;&lt; AssemblyName&gt;&#39;"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- bc30971
- vbc30971
helpviewer_keywords: BC30971
ms.assetid: 75d2e8b5-2fdc-4623-8b32-cba805dab7db
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: a30e5d5aca09e7b74e16dd05cdc0c5c361c1657d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="ltmessagegt-this-error-could-also-be-due-to-mixing-a-file-reference-with-a-project-reference-to-assembly-39ltassemblynamegt39"></a>&lt;mensaje&gt; este error también podría ser debido a la combinación de una referencia de archivo con una referencia de proyecto al ensamblado &#39;&lt; AssemblyName&gt;&#39;
\<mensaje > Este error también podría ser debido a la combinación de una referencia de archivo con una referencia de proyecto al ensamblado '\<assemblyname >. En este caso, intente reemplazar la referencia de archivo a '\<nombredearchivodeensamblado >' en el proyecto '\<projectname1 >' con una referencia de proyecto a '\<projectname2 >'.  
  
 El código del proyecto accede a un miembro de otro proyecto, pero la configuración de la solución no permite que el compilador de [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] resuelva la referencia.  
  
 Para acceder a un tipo definido en otro ensamblado, el compilador de [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] debe tener una referencia a dicho ensamblado. Debe ser una referencia única y no ambigua, que no produzca referencias circulares entre proyectos.  
  
 **Identificador de error:** BC30971  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
1.  Determine qué proyecto produce el mejor ensamblado para que el proyecto haga referencia a este. Para tomar esta decisión, puede usar criterios como la facilidad de acceso a archivos y la frecuencia de las actualizaciones.  
  
2.  En las propiedades del proyecto, agregue una referencia al proyecto que contiene el ensamblado que define el tipo que está usando.  
  
## <a name="see-also"></a>Vea también  
 [Administrar referencias en un proyecto](/visualstudio/ide/managing-references-in-a-project)  
 [Referencias a elementos declarados](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)  
 [NO ESTÁ EN LA COMPILACIÓN: Cómo: agregar o quitar referencias mediante el cuadro de diálogo Agregar referencia](http://msdn.microsoft.com/en-us/3bd75d61-f00c-47c0-86a2-dd1f20e231c9)  
 [Administrar propiedades de soluciones y proyectos](/visualstudio/ide/managing-project-and-solution-properties)  
 [Solucionar problemas de referencias rotas](/visualstudio/ide/troubleshooting-broken-references)
