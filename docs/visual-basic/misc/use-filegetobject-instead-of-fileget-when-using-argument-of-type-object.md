---
title: Use &#39;FileGetObject&#39; en lugar de &#39;FileGet&#39; al usar el argumento de tipo &#39;objeto&#39;
ms.date: 07/20/2015
ms.assetid: 090b8088-895a-482a-9362-606596bac304
ms.openlocfilehash: 2edb80f6df95774e0ea5a7b51e57925845d7ba75
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33640422"
---
# <a name="use-39filegetobject39-instead-of-39fileget39-when-using-argument-of-type-39object39"></a>Use &#39;FileGetObject&#39; en lugar de &#39;FileGet&#39; al usar el argumento de tipo &#39;objeto&#39;
El método `FileGet` incluye un argumento de tipo `Object`. Debe usarse`FileGetObject` en lugar de `FileGet` para evitar ambigüedades.  
  
 Tenga en cuenta que la funcionalidad que proporciona `My.Computer.Filesystem` ofrece mayor facilidad de uso y rendimiento que `FileGet` o `FileGetObject`.  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
1.  Reemplace `FileGet` por `FileGetObject`.  
  
2.  Convierta el argumento `Object` a un tipo más específico.  
  
## <a name="see-also"></a>Vea también  
   
 [My.Computer.FileSystem](xref:Microsoft.VisualBasic.FileIO.FileSystem)
