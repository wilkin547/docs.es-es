---
description: 'Más información acerca de: error de Automation'
title: Error de automatización
ms.date: 07/20/2015
f1_keywords:
- vbrID440
ms.assetid: 2c4be5c5-2f0d-4a2b-96fe-d1b24f08fc4c
ms.openlocfilehash: e4d283b16b4c54e2488fedfc58d3c881cf6b0218
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99797125"
---
# <a name="automation-error"></a>Error de automatización

Se ha producido un error al ejecutar un método u obtener o establecer una propiedad de una variable de objeto. El error se notificó a través de la aplicación que creó el objeto.  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
1. Compruebe las propiedades del objeto `Err` para conocer el origen y naturaleza del error.  
  
2. Use la instrucción `On Error Resume Next` justo antes de la instrucción de acceso y busque los errores justo después de la instrucción de acceso.  
  
## <a name="see-also"></a>Vea también

- [Tipos de error](../../programming-guide/language-features/error-types.md)
- [Hable con nosotros](/visualstudio/ide/feedback-options)
