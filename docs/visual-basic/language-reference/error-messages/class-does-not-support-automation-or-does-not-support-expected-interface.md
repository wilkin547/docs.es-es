---
description: 'Más información acerca de: la clase no admite Automation o no admite la interfaz esperada'
title: Esta clase no admite automatización o no admite la interfaz esperada
ms.date: 07/20/2015
f1_keywords:
- vbrID430
ms.assetid: d985bb7e-e48e-443e-86f2-ddb86758757c
ms.openlocfilehash: cc5ae539064b8d049e2808d916f9f4b75f7e94c9
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99796800"
---
# <a name="class-does-not-support-automation-or-does-not-support-expected-interface"></a>Esta clase no admite automatización o no admite la interfaz esperada

La clase especificada en la llamada a la función `GetObject` o a la función `CreateObject` no ha expuesto una interfaz de programación, o bien el proyecto se ha cambiado de .dll a .exe (o a la inversa).  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
1. Consulte la documentación de la aplicación que creó el objeto para conocer las limitaciones en cuanto al uso de la automatización con esta clase de objeto.  
  
2. Si cambió un proyecto de .dll a .exe o a la inversa, deberá eliminar manualmente el registro del antiguo .dll o .exe.  
  
## <a name="see-also"></a>Vea también

- [Tipos de error](../../programming-guide/language-features/error-types.md)
- [Hable con nosotros](/visualstudio/ide/feedback-options)
