---
title: 'Parámetros de métodos: Referencia de C#'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- methods [C#], parameters
- method parameters [C#]
- parameters [C#]
ms.assetid: 680e39ff-775b-48b0-9f47-4186a5bfc4a1
ms.openlocfilehash: 4011cbd3bc9306b64df87b1fcde48f1f41df8240
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/19/2019
ms.locfileid: "69602043"
---
# <a name="method-parameters-c-reference"></a>Parámetros de métodos (Referencia de C#)

Los parámetros declarados para un método sin [in](./in-parameter-modifier.md), [ref](./ref.md) o [out](./out-parameter-modifier.md) se pasan al método llamado por valor. Ese valor se puede cambiar en el método, pero el cambio se perderá cuando se devuelva el control al procedimiento que ha realizado la llamada. Si usa palabras clave de parámetros de método en la declaración del parámetro, puede modificar este comportamiento.  
  
 Esta sección describe las palabras clave que puede usar para declarar parámetros de métodos:  
  
- [params](./params.md) especifica que este parámetro puede tomar un número variable de argumentos.
  
- [in](./in-parameter-modifier.md) especifica que este parámetro se pasa por referencia, pero solo se lee mediante el método llamado.
  
- [ref](./ref.md) especifica que este parámetro se pasa por referencia y puede ser leído o escrito por el método llamado.
  
- [out](./out-parameter-modifier.md) especifica que este parámetro se pasa por referencia y se escribe mediante el método llamado.
  
## <a name="see-also"></a>Vea también

- [Referencia de C#](../index.md)
- [Guía de programación de C#](../../programming-guide/index.md)
- [Palabras clave de C#](./index.md)
