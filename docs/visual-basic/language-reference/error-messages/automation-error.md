---
title: Error de automatización
ms.date: 07/20/2015
f1_keywords:
- vbrID440
ms.assetid: 2c4be5c5-2f0d-4a2b-96fe-d1b24f08fc4c
ms.openlocfilehash: d62ba57db8bffefb2cfebed705251d87fe285602
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84409899"
---
# <a name="automation-error"></a>Error de automatización

Se ha producido un error al ejecutar un método u obtener o establecer una propiedad de una variable de objeto. El error se notificó a través de la aplicación que creó el objeto.  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
1. Compruebe las propiedades del objeto `Err` para conocer el origen y naturaleza del error.  
  
2. Use la instrucción `On Error Resume Next` justo antes de la instrucción de acceso y busque los errores justo después de la instrucción de acceso.  
  
## <a name="see-also"></a>Consulte también

- [Tipos de error](../../programming-guide/language-features/error-types.md)
- [Hable con nosotros](/visualstudio/ide/feedback-options)
