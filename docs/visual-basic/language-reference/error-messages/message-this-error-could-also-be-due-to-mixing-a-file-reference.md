---
title: "&lt;mensaje&gt; Este error tambi&#233;n puede ser debido a la combinaci&#243;n de una referencia de archivo con una referencia de proyecto en el ensamblado &quot;&lt;nombreDeEnsamblado&gt;&quot; | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "bc30971"
  - "vbc30971"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC30971"
ms.assetid: 75d2e8b5-2fdc-4623-8b32-cba805dab7db
caps.latest.revision: 10
caps.handback.revision: 10
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &lt;mensaje&gt; Este error tambi&#233;n puede ser debido a la combinaci&#243;n de una referencia de archivo con una referencia de proyecto en el ensamblado &quot;&lt;nombreDeEnsamblado&gt;&quot;
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

\<mensaje\> Este error también puede ser debido a la combinación de una referencia de archivo con una referencia de proyecto en el ensamblado "\<nombreDeEnsamblado\>". En este caso, intente reemplazar la referencia de archivo a "\<nombreDeArchivoDeEnsamblado\>" en el proyecto "\<nombreDeProyecto 1\>" con una referencia de proyecto a "\<nombreDeProyecto 2\>".  
  
 El código del proyecto accede a un miembro de otro proyecto, pero la configuración de la solución no permite que el compilador de [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] resuelva la referencia.  
  
 Para acceder a un tipo definido en otro ensamblado, el compilador de [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] debe tener una referencia a dicho ensamblado. Debe ser una referencia única y no ambigua, que no produzca referencias circulares entre proyectos.  
  
 **Identificador de error:** BC30971  
  
### Para corregir este error  
  
1.  Determine qué proyecto produce el mejor ensamblado para que el proyecto haga referencia a este. Para tomar esta decisión, puede usar criterios como la facilidad de acceso a archivos y la frecuencia de las actualizaciones.  
  
2.  En las propiedades del proyecto, agregue una referencia al proyecto que contiene el ensamblado que define el tipo que está usando.  
  
## Vea también  
 [Administrar referencias en un proyecto](/visual-studio/ide/managing-references-in-a-project)   
 [Referencias a elementos declarados](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)   
 [NO ESTÁ EN LA COMPILACIÓN: Cómo: agregar o quitar referencias mediante el cuadro de diálogo Agregar referencia](http://msdn.microsoft.com/es-es/3bd75d61-f00c-47c0-86a2-dd1f20e231c9)   
 [NO ESTÁ EN LA COMPILACIÓN Cómo: Modificar las propiedades y los valores de configuración del proyecto](http://msdn.microsoft.com/es-es/e7184bc5-2f2b-4b4f-aa9a-3ecfcbc48b67)   
 [Solucionar problemas de referencias rotas](/visual-studio/ide/troubleshooting-broken-references)