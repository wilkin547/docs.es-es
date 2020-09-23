---
title: Use 'FileGetObject' en lugar de 'FileGet' al usar el argumento de tipo 'Object'.
ms.date: 07/20/2015
ms.assetid: 090b8088-895a-482a-9362-606596bac304
ms.openlocfilehash: 318a0772a99aa86d9a4633e6021f77616a43fc7e
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2020
ms.locfileid: "91059410"
---
# <a name="use-filegetobject-instead-of-fileget-when-using-argument-of-type-object"></a>Use 'FileGetObject' en lugar de 'FileGet' al usar el argumento de tipo 'Object'.

El método `FileGet` incluye un argumento de tipo `Object`. Debe usarse`FileGetObject` en lugar de `FileGet` para evitar ambigüedades.  
  
 Tenga en cuenta que la funcionalidad que proporciona `My.Computer.Filesystem` ofrece mayor facilidad de uso y rendimiento que `FileGet` o `FileGetObject`.  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
1. Reemplace `FileGet` por `FileGetObject`.  
  
2. Convierta el argumento `Object` a un tipo más específico.  
  
## <a name="see-also"></a>Vea también

- [My. Computer. FileSystem](xref:Microsoft.VisualBasic.FileIO.FileSystem)
