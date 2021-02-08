---
description: 'Más información acerca de: el archivo ya está abierto'
title: Archivo ya abierto
ms.date: 07/20/2015
f1_keywords:
- vbrID55
ms.assetid: d674a0fb-ef16-4cc2-9da7-709a8a07dbea
ms.openlocfilehash: 2f3345c15f4a3095a8e733c2c8424edb25b4dee6
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99796306"
---
# <a name="file-already-open"></a>Archivo ya abierto

A veces, un archivo debe cerrarse antes de que `FileOpen` se produzca otra operación. Entre las causas posibles de este error se incluyen:

- `FileOpen`Se ejecutó una operación de modo de salida secuencial para un archivo que ya está abierto

- Una instrucción hace referencia a un archivo abierto.

## <a name="to-correct-this-error"></a>Para corregir este error

- Cierre el archivo antes de ejecutar la instrucción.

## <a name="see-also"></a>Vea también

- <xref:Microsoft.VisualBasic.FileSystem.FileOpen%2A>
