---
title: Usar &#39; FilePutObject &#39; en lugar de &#39; FilePut &#39; al usar el argumento de tipo &#39; objeto &#39;
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbrUseFilePutObject
ms.assetid: d207b9b7-5898-4c13-8b03-9feefac5f726
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 5612c2bd4dc08f767643d2cd865a2ba1a8210c15
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/21/2017
---
# <a name="use-39fileputobject39-instead-of-39fileput39-when-using-argument-of-type-39object39"></a>Usar &#39; FilePutObject &#39; en lugar de &#39; FilePut &#39; al usar el argumento de tipo &#39; objeto &#39;
El `FilePut` método incluye un argumento de tipo `Object`. Debe usarse`FilePutObject` en lugar de `FilePut` para evitar ambigüedades.  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
-   Reemplace `FilePut` por `FilePutObject`.  
  
-   Convierta el argumento `Object` a un tipo más específico.  
  
-   Use la funcionalidad disponible en el objeto `My.Computer.FileSystem` .  
  
## <a name="see-also"></a>Vea también  
   
 [My.Computer.FileSystem](xref:Microsoft.VisualBasic.FileIO.FileSystem)  
 [My.Computer.FileSystem.WriteAllBytes](xref:Microsoft.VisualBasic.MyServices.FileSystemProxy.WriteAllBytes%2A)
