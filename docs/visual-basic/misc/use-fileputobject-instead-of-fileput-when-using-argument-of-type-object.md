---
title: Use 'FilePutObject' en lugar de 'FilePut' al usar el argumento de tipo 'Object'.
ms.date: 07/20/2015
f1_keywords:
- vbrUseFilePutObject
ms.assetid: d207b9b7-5898-4c13-8b03-9feefac5f726
ms.openlocfilehash: bf1f50d0d8eb9b0b8518075b0e48f40645a02a25
ms.sourcegitcommit: e08b319358a8025cc6aa38737854f7bdb87183d6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/29/2019
ms.locfileid: "64913215"
---
# <a name="use-fileputobject-instead-of-fileput-when-using-argument-of-type-object"></a>Use 'FilePutObject' en lugar de 'FilePut' al usar el argumento de tipo 'Object'.
El método `FilePut` incluye un argumento de tipo `Object`. Debe usarse`FilePutObject` en lugar de `FilePut` para evitar ambigüedades.  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
- Reemplace `FilePut` por `FilePutObject`.  
  
- Convierta el argumento `Object` a un tipo más específico.  
  
- Use la funcionalidad disponible en el objeto `My.Computer.FileSystem` .  
  
## <a name="see-also"></a>Vea también

- [My.Computer.FileSystem](xref:Microsoft.VisualBasic.FileIO.FileSystem)
- [My.Computer.FileSystem.WriteAllBytes](xref:Microsoft.VisualBasic.MyServices.FileSystemProxy.WriteAllBytes%2A)
