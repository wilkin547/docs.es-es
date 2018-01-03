---
title: Necesaria una referencia al ensamblado &#39; &lt;assemblyname&gt;&#39; que contiene la clase base &#39;&lt; ClassName&gt;&#39;
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- bc30007
- vbc30007
helpviewer_keywords: BC30007
ms.assetid: 5f34cf47-6c6e-4954-bd8e-d6b020b75fb7
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 39fa33a655b311ee39466c18cefdb0bf07a92720
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/21/2017
---
# <a name="reference-required-to-assembly-39ltassemblynamegt39-containing-the-base-class-39ltclassnamegt39"></a>Necesaria una referencia al ensamblado &#39; &lt;assemblyname&gt;&#39; que contiene la clase base &#39;&lt; ClassName&gt;&#39;
Necesaria una referencia al ensamblado '\<assemblyname >' que contiene la clase base\<classname >'. Agregue una al proyecto.  
  
 La clase está definida en una biblioteca de vínculos dinámicos (DLL) o un ensamblado al que no se hace referencia directamente en el proyecto. El compilador de [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] necesita una referencia para evitar la ambigüedad en caso de que la clase esté definida en más de una DLL o un ensamblado.  
  
 **Identificador de error:** BC30007  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
-   Incluya el nombre de la DLL o el ensamblado no referenciados en las referencias del proyecto.  
  
## <a name="see-also"></a>Vea también  
   
 [Administrar referencias en un proyecto](/visualstudio/ide/managing-references-in-a-project)  
 [Solucionar problemas de referencias rotas](/visualstudio/ide/troubleshooting-broken-references)
