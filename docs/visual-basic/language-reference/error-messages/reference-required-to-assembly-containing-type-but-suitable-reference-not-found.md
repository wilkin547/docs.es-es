---
title: "Es necesaria una referencia al ensamblado &#39;&lt;assemblyidentity&gt;&#39; que contiene el tipo &#39;&lt;typename&gt;&#39;, pero no se pudo encontrar una referencia adecuada debido a la ambig&#252;edad entre los proyectos &#39;&lt;projectname1&gt;&#39; y &#39;&lt;projectname2&gt;&#39; | Microsoft Docs"
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
  - "bc30969"
  - "vbc30969"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC30969"
ms.assetid: 1b29dbc5-8268-45fe-bfc2-b2070a5c845c
caps.latest.revision: 11
caps.handback.revision: 11
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Es necesaria una referencia al ensamblado &#39;&lt;assemblyidentity&gt;&#39; que contiene el tipo &#39;&lt;typename&gt;&#39;, pero no se pudo encontrar una referencia adecuada debido a la ambig&#252;edad entre los proyectos &#39;&lt;projectname1&gt;&#39; y &#39;&lt;projectname2&gt;&#39;
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Una expresión usa un tipo como, por ejemplo, una clase, estructura, interfaz, enumeración o delegado, que se define fuera del proyecto. Sin embargo, hay referencias de proyectos a más de un ensamblado que definen ese tipo.  
  
 Los proyectos citados generan ensamblados con el mismo nombre. Por lo tanto, el compilador no puede determinar qué ensamblado debe usar para el tipo al que se está accediendo.  
  
 Para acceder a un tipo definido en otro ensamblado, el compilador de [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] debe tener una referencia a dicho ensamblado. Debe ser una referencia única y no ambigua, que no produzca referencias circulares entre proyectos.  
  
 **Identificador de error:** BC30969  
  
### Para corregir este error  
  
1.  Determine qué proyecto produce el mejor ensamblado para que el proyecto haga referencia a este. Para tomar esta decisión, puede usar criterios como la facilidad de acceso a archivos y la frecuencia de las actualizaciones.  
  
2.  En las propiedades del proyecto, agregue una referencia al archivo que contiene el ensamblado que define el tipo que está usando.  
  
## Vea también  
 [Administrar referencias en un proyecto](/visual-studio/ide/managing-references-in-a-project)   
 [Referencias a elementos declarados](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)   
 [NO ESTÁ EN LA COMPILACIÓN: Cómo: agregar o quitar referencias mediante el cuadro de diálogo Agregar referencia](http://msdn.microsoft.com/es-es/3bd75d61-f00c-47c0-86a2-dd1f20e231c9)   
 [NO ESTÁ EN LA COMPILACIÓN Cómo: Modificar las propiedades y los valores de configuración del proyecto](http://msdn.microsoft.com/es-es/e7184bc5-2f2b-4b4f-aa9a-3ecfcbc48b67)   
 [Solucionar problemas de referencias rotas](/visual-studio/ide/troubleshooting-broken-references)