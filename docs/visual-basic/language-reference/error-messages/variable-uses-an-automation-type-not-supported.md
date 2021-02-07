---
description: 'Más información acerca de: la variable utiliza un tipo de automatización no compatible en Visual Basic'
title: La variable utiliza un tipo de automatización no compatible
ms.date: 07/20/2015
f1_keywords:
- vbrID458
ms.assetid: bde4f4da-493b-452c-b6e4-1d370edba4cd
ms.openlocfilehash: 9aa8f8a2a49e54c547dc47d38305d40f855b1815
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99666152"
---
# <a name="variable-uses-an-automation-type-not-supported-in-visual-basic"></a>La variable utiliza un tipo de Automation no compatible con Visual Basic

Ha intentado usar una variable definida en una biblioteca de tipos o una biblioteca de objetos que tiene un tipo de datos no admitido por Visual Basic.

## <a name="to-correct-this-error"></a>Para corregir este error

- Use una variable de un tipo reconocido por Visual Basic.

     o bien

- Si se produce este error al usar `FileGet` o `FileGetObject` , asegúrese de que el archivo que está intentando usar se escribió en con `FilePut` o `FilePutObject` .

## <a name="see-also"></a>Vea también

- [Tipo de datos](../data-types/index.md)
