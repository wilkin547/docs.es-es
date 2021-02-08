---
description: "Más información sobre: BC30617: las instrucciones ' module ' solo pueden aparecer en el nivel de archivo o de espacio de nombres"
title: Las instrucciones 'Module' sólo pueden ocurrir en el nivel de archivo o de espacio de nombres
ms.date: 07/20/2015
f1_keywords:
- bc30617
- vbc30617
helpviewer_keywords:
- BC30617
ms.assetid: 5e9de8e5-d26b-4fb2-9e28-814413fe9cef
ms.openlocfilehash: f5c3ea0cd1c08fb0243043ae50e707e2c59b00f2
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99795786"
---
# <a name="bc30617-module-statements-can-occur-only-at-file-or-namespace-level"></a>BC30617: las instrucciones ' module ' solo pueden aparecer en el nivel de archivo o de espacio de nombres

`Module` las instrucciones deben aparecer en la parte superior del archivo de código fuente inmediatamente después de las `Option` `Imports` instrucciones y, los atributos globales y las declaraciones de espacio de nombres, pero antes de todas las demás declaraciones.

 **Identificador de error:** BC30617

## <a name="to-correct-this-error"></a>Para corregir este error

- Mueva la instrucción `Module` a la parte superior de la declaración del espacio de nombres o el archivo de código fuente.

## <a name="see-also"></a>Vea también

- [Module (Instrucción)](../statements/module-statement.md)
