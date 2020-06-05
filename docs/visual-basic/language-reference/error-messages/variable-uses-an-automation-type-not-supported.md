---
title: La variable utiliza un tipo de automatización no compatible
ms.date: 07/20/2015
f1_keywords:
- vbrID458
ms.assetid: bde4f4da-493b-452c-b6e4-1d370edba4cd
ms.openlocfilehash: 7d52189e31823b63547c757434847c0e1717aada
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84406552"
---
# <a name="variable-uses-an-automation-type-not-supported-in-visual-basic"></a>La variable utiliza un tipo de Automation no compatible con Visual Basic

Ha intentado usar una variable definida en una biblioteca de tipos o una biblioteca de objetos que tiene un tipo de datos no admitido por Visual Basic.

## <a name="to-correct-this-error"></a>Para corregir este error

- Use una variable de un tipo reconocido por Visual Basic.

     O bien

- Si se produce este error al usar `FileGet` o `FileGetObject` , asegúrese de que el archivo que está intentando usar se escribió en con `FilePut` o `FilePutObject` .

## <a name="see-also"></a>Consulte también

- [Tipos de datos](../data-types/index.md)
