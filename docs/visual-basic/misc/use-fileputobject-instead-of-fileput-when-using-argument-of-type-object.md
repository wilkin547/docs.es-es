---
description: "Más información acerca de: Use ' FilePutObject ' en lugar de ' FilePut ' al usar el argumento de tipo ' Object '"
title: Use 'FilePutObject' en lugar de 'FilePut' al usar el argumento de tipo 'Object'.
ms.date: 07/20/2015
f1_keywords:
- vbrUseFilePutObject
ms.assetid: d207b9b7-5898-4c13-8b03-9feefac5f726
ms.openlocfilehash: 5e5822999aa39bff4d43f83a2719341034cdcadc
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100460103"
---
# <a name="use-fileputobject-instead-of-fileput-when-using-argument-of-type-object"></a>Use 'FilePutObject' en lugar de 'FilePut' al usar el argumento de tipo 'Object'.

El método `FilePut` incluye un argumento de tipo `Object`. Debe usarse`FilePutObject` en lugar de `FilePut` para evitar ambigüedades.  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
- Reemplace `FilePut` por `FilePutObject`.  
  
- Convierta el argumento `Object` a un tipo más específico.  
  
- Use la funcionalidad disponible en el objeto `My.Computer.FileSystem` .  
  
## <a name="see-also"></a>Consulte también

- [My. Computer. FileSystem](xref:Microsoft.VisualBasic.FileIO.FileSystem)
- [My. Computer. FileSystem. WriteAllBytes](xref:Microsoft.VisualBasic.MyServices.FileSystemProxy.WriteAllBytes%2A)
