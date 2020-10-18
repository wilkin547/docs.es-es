---
title: Las instrucciones 'Module' sólo pueden ocurrir en el nivel de archivo o de espacio de nombres
ms.date: 07/20/2015
f1_keywords:
- bc30617
- vbc30617
helpviewer_keywords:
- BC30617
ms.assetid: 5e9de8e5-d26b-4fb2-9e28-814413fe9cef
ms.openlocfilehash: b946a527d3de3a030ac03691c77afcf440f518ee
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "92160319"
---
# <a name="bc30617-module-statements-can-occur-only-at-file-or-namespace-level"></a>BC30617: las instrucciones ' module ' solo pueden aparecer en el nivel de archivo o de espacio de nombres

`Module` las instrucciones deben aparecer en la parte superior del archivo de código fuente inmediatamente después de las `Option` `Imports` instrucciones y, los atributos globales y las declaraciones de espacio de nombres, pero antes de todas las demás declaraciones.

 **Identificador de error:** BC30617

## <a name="to-correct-this-error"></a>Para corregir este error

- Mueva la instrucción `Module` a la parte superior de la declaración del espacio de nombres o el archivo de código fuente.

## <a name="see-also"></a>Vea también

- [Module (Instrucción)](../statements/module-statement.md)
