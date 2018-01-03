---
title: Usar &#39; FileGetObject &#39; en lugar de &#39; FileGet &#39; al usar el argumento de tipo &#39; objeto &#39;
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-visual-basic
ms.topic: article
ms.assetid: 090b8088-895a-482a-9362-606596bac304
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 2c5be466a8a0339bdb57818755d85a26d632d774
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/21/2017
---
# <a name="use-39filegetobject39-instead-of-39fileget39-when-using-argument-of-type-39object39"></a>Usar &#39; FileGetObject &#39; en lugar de &#39; FileGet &#39; al usar el argumento de tipo &#39; objeto &#39;
El método `FileGet` incluye un argumento de tipo `Object`. Debe usarse`FileGetObject` en lugar de `FileGet` para evitar ambigüedades.  
  
 Tenga en cuenta que la funcionalidad que proporciona `My.Computer.Filesystem` ofrece mayor facilidad de uso y rendimiento que `FileGet` o `FileGetObject`.  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
1.  Reemplace `FileGet` por `FileGetObject`.  
  
2.  Convierta el argumento `Object` a un tipo más específico.  
  
## <a name="see-also"></a>Vea también  
   
 [My.Computer.FileSystem](xref:Microsoft.VisualBasic.FileIO.FileSystem)
