---
title: Usar &#39; FilePutObject &#39; en lugar de &#39; FilePut &#39; al usar el argumento de tipo &#39; objeto &#39;
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vbrUseFilePutObject
ms.assetid: d207b9b7-5898-4c13-8b03-9feefac5f726
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 8cba4af206e2dbf767fdb883ec81229a67842c57
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="use-39fileputobject39-instead-of-39fileput39-when-using-argument-of-type-39object39"></a>Usar &#39; FilePutObject &#39; en lugar de &#39; FilePut &#39; al usar el argumento de tipo &#39; objeto &#39;
El `FilePut` método incluye un argumento de tipo `Object`. Debe usarse`FilePutObject` en lugar de `FilePut` para evitar ambigüedades.  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
-   Reemplace `FilePut` por `FilePutObject`.  
  
-   Convierta el argumento `Object` a un tipo más específico.  
  
-   Use la funcionalidad disponible en el objeto `My.Computer.FileSystem` .  
  
## <a name="see-also"></a>Vea también  
 [NO está en la compilación: FilePutObject (función)](http://msdn.microsoft.com/en-us/a0f52a1c-5ecc-4945-b18c-03147af61d6b)  
 [My.Computer.FileSystem (objeto)](../../visual-basic/language-reference/objects/my-computer-filesystem-object.md)  
 [Método My.Computer.FileSystem.WriteAllBytes](http://msdn.microsoft.com/en-us/b1a24dc1-eac8-4e22-8ffa-cc3bacbaf826)
