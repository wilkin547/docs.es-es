---
title: Consideraciones sobre versiones y actualizaciones para desarrolladores de C#
description: La incorporación de nuevas características de lenguajes en la biblioteca puede afectar al código que la utiliza.
ms.date: 09/19/2018
ms.openlocfilehash: 3ffe2f6fd64a391fddf28233dccb022c95851884
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "79398152"
---
# <a name="version-and-update-considerations-for-c-developers"></a>Consideraciones sobre versiones y actualizaciones para desarrolladores de C#

La compatibilidad es un objetivo muy importante cuando se agregan nuevas características al lenguaje C#. En la mayoría de los casos, se puede volver a compilar el código existente con una nueva versión de compilador sin ningún problema.

Al adoptar nuevas características del lenguaje en una biblioteca, puede requerirse más atención. Puede crear una biblioteca con características que se encuentran en la última versión y necesita asegurarse de que las aplicaciones creadas con versiones anteriores del compilador pueden usarla. O bien puede actualizar una biblioteca existente, con la posibilidad de que muchos de los usuarios aún no tengan versiones actualizadas. Cuando tome decisiones sobre la adopción de nuevas características, se deberán tener en cuenta dos variaciones de compatibilidad: compatibilidad binaria y compatibilidad con el origen.

## <a name="binary-compatible-changes"></a>Cambios compatibles con elementos binarios

Los cambios en la biblioteca son **compatibles con elementos binarios** cuando se puede utilizar la biblioteca actualizada sin tener que volver a crear aplicaciones y bibliotecas que la usan. No es necesario volver a compilar ensamblados dependientes ni realizar ningún cambio en el código fuente. Los cambios compatibles con los elementos binarios también son compatibles con el origen.

## <a name="source-compatible-changes"></a>Cambios compatibles con el origen

Los cambios en la biblioteca son **compatibles con el origen** cuando las aplicaciones y bibliotecas que usan la biblioteca no requieren cambios de código fuente, pero el origen debe volver a compilarse con la nueva versión para que funcione correctamente.

## <a name="incompatible-changes"></a>Cambios incompatibles

Si un cambio no es **compatible con el origen** ni es **compatible con los elementos binarios**, se necesitan cambios del código junto con la recompilación en las bibliotecas y aplicaciones dependientes.

## <a name="evaluate-your-library"></a>Evaluar la biblioteca

Estos conceptos de compatibilidad afectan a las declaraciones públicas y protegidas de la biblioteca, no a su implementación interna. La adopción interna de nuevas características siempre es **compatible con los elementos binarios**.  

Los cambios **compatibles con los elementos binarios** proporcionan la nueva sintaxis que genera el mismo código compilado para las declaraciones públicas que la sintaxis anterior. Por ejemplo, cambiar un método a un miembro con cuerpo de expresión es un **cambio compatible con un elemento binario**:

Código original:

```csharp
public double CalculateSquare(double value)
{
    return value * value;
}
```

Nuevo código:

```csharp
public double CalculateSquare(double value) => value * value;
```

Los cambios **compatibles con el origen** presentan la sintaxis que cambia el código compilado para un miembro público, pero de una forma compatible con los sitios de llamada existentes. Por ejemplo, cambiar una firma del método a partir de un parámetro de valor a `in` mediante un parámetro de referencia es compatible con el origen, pero no lo es con los elementos binarios:

Código original:

```csharp
public double CalculateSquare(double value) => value * value;
```

Nuevo código:

```csharp
public double CalculateSquare(in double value) => value * value;
```

En el artículo de [novedades](index.md), observe si la presentación de una característica que afecta a las declaraciones públicas es compatible con el origen o con los elementos binarios.
