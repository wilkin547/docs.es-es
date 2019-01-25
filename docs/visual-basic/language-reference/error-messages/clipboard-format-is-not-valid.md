---
title: Formato del Portapapeles no válido
ms.date: 07/20/2015
f1_keywords:
- vbrID460
ms.assetid: 71a4a045-65bb-417d-b3bd-99a9fa3c53f6
ms.openlocfilehash: 0a5d06b381df3af8de1d092b600239c9acfce39a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54735784"
---
# <a name="clipboard-format-is-not-valid"></a>Formato del Portapapeles no válido
El formato de Portapapeles especificado no es compatible con el método que se está ejecutando. Entre las posibles causas de este error son:  
  
-   Usar el Portapapeles `GetText` o `SetText` método con un formato de Portapapeles distinto `vbCFText` o `vbCFLink`.  
  
-   Usar el Portapapeles `GetData` o `SetData` método con un formato de Portapapeles distinto `vbCFBitmap`, `vbCFDIB`, o `vbCFMetafile`.  
  
-   Mediante el `GetData` o `SetData` métodos de un `DataObject` con un formato de Portapapeles en el intervalo reservado por Microsoft Windows para formatos registrados (& HC000 - & HFFFF), cuando ese formato de Portapapeles no se ha registrado con Microsoft Windows .  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
-   Quitar el formato no válido y especifique uno válido.  
  
## <a name="see-also"></a>Vea también
- [Portapapeles: Agregar otros formatos](/cpp/mfc/clipboard-adding-other-formats)
