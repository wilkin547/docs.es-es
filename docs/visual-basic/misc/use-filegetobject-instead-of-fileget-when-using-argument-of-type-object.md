---
description: "Más información acerca de: Use ' FileGetObject ' en lugar de ' FileGet ' al usar el argumento de tipo ' Object '"
title: Use 'FileGetObject' en lugar de 'FileGet' al usar el argumento de tipo 'Object'.
ms.date: 07/20/2015
ms.assetid: 090b8088-895a-482a-9362-606596bac304
ms.openlocfilehash: 4481fdced961cacf0e652c141601efa13bec776b
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100471167"
---
# <a name="use-filegetobject-instead-of-fileget-when-using-argument-of-type-object"></a>Use 'FileGetObject' en lugar de 'FileGet' al usar el argumento de tipo 'Object'.

El método `FileGet` incluye un argumento de tipo `Object`. Debe usarse`FileGetObject` en lugar de `FileGet` para evitar ambigüedades.  
  
 Tenga en cuenta que la funcionalidad que proporciona `My.Computer.Filesystem` ofrece mayor facilidad de uso y rendimiento que `FileGet` o `FileGetObject`.  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
1. Reemplace `FileGet` por `FileGetObject`.  
  
2. Convierta el argumento `Object` a un tipo más específico.  
  
## <a name="see-also"></a>Consulte también

- [My. Computer. FileSystem](xref:Microsoft.VisualBasic.FileIO.FileSystem)
