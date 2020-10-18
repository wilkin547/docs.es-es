---
title: Archivo ya abierto
ms.date: 07/20/2015
f1_keywords:
- vbrID55
ms.assetid: d674a0fb-ef16-4cc2-9da7-709a8a07dbea
ms.openlocfilehash: ce8f8bf96d7355e45b2df82e8a131472c2ed2367
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "92162757"
---
# <a name="file-already-open"></a>Archivo ya abierto

A veces, un archivo debe cerrarse antes de que `FileOpen` se produzca otra operación. Entre las causas posibles de este error se incluyen:

- `FileOpen`Se ejecutó una operación de modo de salida secuencial para un archivo que ya está abierto

- Una instrucción hace referencia a un archivo abierto.

## <a name="to-correct-this-error"></a>Para corregir este error

- Cierre el archivo antes de ejecutar la instrucción.

## <a name="see-also"></a>Vea también

- <xref:Microsoft.VisualBasic.FileSystem.FileOpen%2A>
