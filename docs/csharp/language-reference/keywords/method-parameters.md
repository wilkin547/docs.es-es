---
title: 'Parámetros de métodos: Referencia de C#'
ms.date: 07/20/2015
helpviewer_keywords:
- methods [C#], parameters
- method parameters [C#]
- parameters [C#]
ms.assetid: 680e39ff-775b-48b0-9f47-4186a5bfc4a1
ms.openlocfilehash: 2cc7f9178fa5c1a040be9d45ba66fac292bb0e28
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "75713383"
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
