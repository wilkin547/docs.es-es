---
title: Esta clase no admite automatización o no admite la interfaz esperada
ms.date: 07/20/2015
f1_keywords:
- vbrID430
ms.assetid: d985bb7e-e48e-443e-86f2-ddb86758757c
ms.openlocfilehash: aa97ae420a0a289979fe86db373c635361dc6475
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "90874647"
---
# <a name="class-does-not-support-automation-or-does-not-support-expected-interface"></a>Esta clase no admite automatización o no admite la interfaz esperada

La clase especificada en la llamada a la función `GetObject` o a la función `CreateObject` no ha expuesto una interfaz de programación, o bien el proyecto se ha cambiado de .dll a .exe (o a la inversa).  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
1. Consulte la documentación de la aplicación que creó el objeto para conocer las limitaciones en cuanto al uso de la automatización con esta clase de objeto.  
  
2. Si cambió un proyecto de .dll a .exe o a la inversa, deberá eliminar manualmente el registro del antiguo .dll o .exe.  
  
## <a name="see-also"></a>Consulte también

- [Tipos de errores](../../programming-guide/language-features/error-types.md)
- [Hable con nosotros](/visualstudio/ide/feedback-options)
