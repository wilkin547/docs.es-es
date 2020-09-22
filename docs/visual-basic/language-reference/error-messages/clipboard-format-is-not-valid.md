---
title: Formato del Portapapeles no válido
ms.date: 07/20/2015
f1_keywords:
- vbrID460
ms.assetid: 71a4a045-65bb-417d-b3bd-99a9fa3c53f6
ms.openlocfilehash: 429d1e120a0044152a358a87663eb09989f45b0e
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "90874589"
---
# <a name="clipboard-format-is-not-valid"></a>Formato del Portapapeles no válido

El formato del portapapeles especificado es incompatible con el método que se está ejecutando. Entre las posibles causas de este error se encuentran:  
  
- Usar el método o del portapapeles `GetText` `SetText` con un formato de Portapapeles distinto de `vbCFText` o `vbCFLink` .  
  
- Usar el método o del portapapeles `GetData` `SetData` con un formato de Portapapeles distinto de `vbCFBitmap` , `vbCFDIB` o `vbCFMetafile` .  
  
- Usar los `GetData` `SetData` métodos o de `DataObject` con un formato de Portapapeles en el intervalo reservado por Microsoft Windows para los formatos registrados (&HC000-&HFFFF), cuando el formato del portapapeles no se ha registrado con Microsoft Windows.  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
- Quite el formato no válido y especifique uno válido.  
  
## <a name="see-also"></a>Consulte también

- [Portapapeles: agregar otros formatos](/cpp/mfc/clipboard-adding-other-formats)
