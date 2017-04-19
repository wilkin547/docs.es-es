---
title: Necesaria una referencia al ensamblado &quot;&lt;assemblyname&gt;&quot;que contiene la clase base&quot;&lt;classname&gt;&quot; | Documentos de Microsoft
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc30007
- vbc30007
dev_langs:
- VB
helpviewer_keywords:
- BC30007
ms.assetid: 5f34cf47-6c6e-4954-bd8e-d6b020b75fb7
caps.latest.revision: 9
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 2692478864007c787eb19367109e6ce01882ffb1
ms.lasthandoff: 03/13/2017

---
# <a name="reference-required-to-assembly-39ltassemblynamegt39-containing-the-base-class-39ltclassnamegt39"></a>Necesaria una referencia al ensamblado '&lt;assemblyname&gt;'que contiene la clase base'&lt;classname&gt;'
Necesaria una referencia al ensamblado '\<assemblyname >' que contenga la clase base\<classname >'. Agregue una al proyecto.  
  
 La clase está definida en una biblioteca de vínculos dinámicos (DLL) o un ensamblado al que no se hace referencia directamente en el proyecto. El [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] compilador requiere una referencia para evitar la ambigüedad en caso de que la clase está definida en más de una DLL o ensamblado.  
  
 **Identificador de error:** BC30007  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
-   Incluya el nombre de la DLL o ensamblado no referenciados en las referencias del proyecto.  
  
## <a name="see-also"></a>Vea también  
 [Cómo: Agregar o quitar referencias utilizando el cuadro de diálogo Agregar referencia](http://msdn.microsoft.com/en-us/3bd75d61-f00c-47c0-86a2-dd1f20e231c9)   
 [Administrar referencias en un proyecto](https://docs.microsoft.com/visualstudio/ide/managing-references-in-a-project)   
 [Solucionar problemas de referencias rotas](https://docs.microsoft.com/visualstudio/ide/troubleshooting-broken-references)
