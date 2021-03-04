---
description: 'Más información acerca de: error de Automation'
title: Error de automatización
ms.date: 07/20/2015
f1_keywords:
- vbrID440
ms.assetid: 2c4be5c5-2f0d-4a2b-96fe-d1b24f08fc4c
ms.openlocfilehash: bf3e61bb9b8fec9a831d211b70abdca322c1fe06
ms.sourcegitcommit: 42d436ebc2a7ee02fc1848c7742bc7d80e13fc2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/04/2021
ms.locfileid: "102106610"
---
# <a name="automation-error"></a>Error de automatización

Se ha producido un error al ejecutar un método u obtener o establecer una propiedad de una variable de objeto. El error se notificó a través de la aplicación que creó el objeto.  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
1. Compruebe las propiedades del objeto `Err` para conocer el origen y naturaleza del error.  
  
2. Use la instrucción `On Error Resume Next` justo antes de la instrucción de acceso y busque los errores justo después de la instrucción de acceso.  
  
## <a name="see-also"></a>Consulte también

- [Tipos de error](../../programming-guide/language-features/error-types.md)
- [Opciones de comentarios de Visual Studio](/visualstudio/ide/feedback-options)
