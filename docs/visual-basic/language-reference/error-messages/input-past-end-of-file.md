---
description: 'Más información sobre: entrada más allá del final del archivo'
title: Se sobrepasó el final del archivo
ms.date: 07/20/2015
f1_keywords:
- vbrID62
ms.assetid: 65292704-6e7d-4622-9f50-eb655a59b016
ms.openlocfilehash: b65a57bdc56367518a93880be28781e56c9b99cc
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99796046"
---
# <a name="input-past-end-of-file"></a>Se sobrepasó el final del archivo

Una `Input` instrucción está leyendo de un archivo que está vacío o uno en el que se usan todos los datos, o bien se ha usado la `EOF` función con un archivo abierto para el acceso binario.  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
1. Utilice la `EOF` función inmediatamente antes de la `Input` instrucción para detectar el final del archivo.  
  
2. Si el archivo se abre para el acceso binario, use `Seek` y `Loc` .  
  
## <a name="see-also"></a>Vea también

- <xref:Microsoft.VisualBasic.FileSystem.Input%2A>
- <xref:Microsoft.VisualBasic.FileSystem.EOF%2A>
- <xref:Microsoft.VisualBasic.FileSystem.Seek%2A>
- <xref:Microsoft.VisualBasic.FileSystem.Loc%2A>
