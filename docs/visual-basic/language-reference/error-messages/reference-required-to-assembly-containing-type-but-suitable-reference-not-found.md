---
title: Necesaria una referencia al ensamblado &#39; &lt;identidadensamblado&gt; &#39; que contiene el tipo &#39; &lt;typename&gt;&#39;, pero no se pudo encontrar una referencia adecuada debido a la ambigüedad entre proyectos &#39; &lt;projectname1&gt; &#39; y &#39; &lt;projectname2&gt;&#39;
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc30969
- vbc30969
helpviewer_keywords:
- BC30969
ms.assetid: 1b29dbc5-8268-45fe-bfc2-b2070a5c845c
caps.latest.revision: 11
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 69b1184d47e427bd985c3b18135d4a0ac4d91410
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/26/2018
---
# <a name="reference-required-to-assembly-39ltassemblyidentitygt39-containing-type-39lttypenamegt39-but-a-suitable-reference-could-not-be-found-due-to-ambiguity-between-projects-39ltprojectname1gt39-and-39ltprojectname2gt39"></a>Necesaria una referencia al ensamblado &#39; &lt;identidadensamblado&gt; &#39; que contiene el tipo &#39; &lt;typename&gt;&#39;, pero no se pudo encontrar una referencia adecuada debido a la ambigüedad entre proyectos &#39; &lt;projectname1&gt; &#39; y &#39; &lt;projectname2&gt;&#39;
Una expresión usa un tipo como, por ejemplo, una clase, estructura, interfaz, enumeración o delegado, que se define fuera del proyecto. Sin embargo, hay referencias de proyectos a más de un ensamblado que definen ese tipo.  
  
 Los proyectos citados generan ensamblados con el mismo nombre. Por lo tanto, el compilador no puede determinar qué ensamblado debe usar para el tipo al que se está accediendo.  
  
 Para obtener acceso a un tipo definido en otro ensamblado, el compilador de Visual Basic debe tener una referencia a dicho ensamblado. Debe ser una referencia única y no ambigua, que no produzca referencias circulares entre proyectos.  
  
 **Identificador de error:** BC30969  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
1.  Determine qué proyecto produce el mejor ensamblado para que el proyecto haga referencia a este. Para tomar esta decisión, puede usar criterios como la facilidad de acceso a archivos y la frecuencia de las actualizaciones.  
  
2.  En las propiedades del proyecto, agregue una referencia al archivo que contiene el ensamblado que define el tipo que está usando.  
  
## <a name="see-also"></a>Vea también  
 [Administrar referencias en un proyecto](/visualstudio/ide/managing-references-in-a-project)  
 [Referencias a elementos declarados](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)  
   
 [Administrar propiedades de soluciones y proyectos](/visualstudio/ide/managing-project-and-solution-properties)  
 [Solucionar problemas de referencias rotas](/visualstudio/ide/troubleshooting-broken-references)
