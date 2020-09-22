---
title: Archivo ya abierto
ms.date: 07/20/2015
f1_keywords:
- vbrID55
ms.assetid: d674a0fb-ef16-4cc2-9da7-709a8a07dbea
ms.openlocfilehash: 97f9e13e6802e793f7c7baf1f03ec51205eb6d42
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "90874182"
---
# <a name="file-already-open"></a>Archivo ya abierto

A veces, un archivo debe cerrarse antes de que `FileOpen` se produzca otra operación. Entre las causas posibles de este error se incluyen:  
  
- `FileOpen`Se ejecutó una operación de modo de salida secuencial para un archivo que ya está abierto  
  
- Una instrucción hace referencia a un archivo abierto.  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
1. Cierre el archivo antes de ejecutar la instrucción.  
  
## <a name="see-also"></a>Consulte también

- <xref:Microsoft.VisualBasic.FileSystem.FileOpen%2A>
