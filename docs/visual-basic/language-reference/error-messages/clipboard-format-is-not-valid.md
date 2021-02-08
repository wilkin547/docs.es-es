---
description: 'Más información acerca de: el formato del portapapeles no es válido'
title: Formato del Portapapeles no válido
ms.date: 07/20/2015
f1_keywords:
- vbrID460
ms.assetid: 71a4a045-65bb-417d-b3bd-99a9fa3c53f6
ms.openlocfilehash: 58ba6197a14b005cf61d0783e19cb3f957dd2fca
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99796761"
---
# <a name="clipboard-format-is-not-valid"></a>Formato del Portapapeles no válido

El formato del portapapeles especificado es incompatible con el método que se está ejecutando. Entre las posibles causas de este error se encuentran:  
  
- Usar el método o del portapapeles `GetText` `SetText` con un formato de Portapapeles distinto de `vbCFText` o `vbCFLink` .  
  
- Usar el método o del portapapeles `GetData` `SetData` con un formato de Portapapeles distinto de `vbCFBitmap` , `vbCFDIB` o `vbCFMetafile` .  
  
- Usar los `GetData` `SetData` métodos o de `DataObject` con un formato de Portapapeles en el intervalo reservado por Microsoft Windows para los formatos registrados (&HC000-&HFFFF), cuando el formato del portapapeles no se ha registrado con Microsoft Windows.  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
- Quite el formato no válido y especifique uno válido.  
  
## <a name="see-also"></a>Vea también

- [Portapapeles: agregar otros formatos](/cpp/mfc/clipboard-adding-other-formats)
