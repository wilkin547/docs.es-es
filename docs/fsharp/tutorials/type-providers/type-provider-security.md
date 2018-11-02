---
title: Seguridad del proveedor de tipos
description: 'Obtenga información sobre la seguridad del proveedor de tipos en F #, incluida la forma de cambiar la configuración de confianza de un proveedor de tipos.'
ms.date: 05/16/2016
ms.openlocfilehash: 26f95ad3950b37a668c497f293b9941ed13a18c7
ms.sourcegitcommit: db8b83057d052c1f9f249d128b08d4423af0f7c2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/02/2018
ms.locfileid: "43861912"
---
# <a name="type-provider-security"></a>Seguridad del proveedor de tipos

Los proveedores de tipos son ensamblados (DLL) al que hace referencia su proyecto de F # o script que contienen código para conectarse a orígenes de datos externos y la información de este tipo de superficie para el entorno de tipo de F #. Normalmente, solo se ejecuta código en ensamblados de referencia, cuando compile y, a continuación, ejecute el código (o en el caso de una secuencia de comandos, envíe el código de F # Interactive). Sin embargo, un ensamblado de proveedor de tipo se ejecutará dentro de Visual Studio cuando simplemente se puede examinar el código en el editor. Esto sucede porque los proveedores de tipos deben ejecutar para agregar información adicional en el editor, como información rápida sobre herramientas, las finalizaciones de IntelliSense y así sucesivamente. Como resultado, hay consideraciones de seguridad adicional para el tipo de ensamblados de proveedor, ya que se ejecutan automáticamente dentro del proceso de Visual Studio.

## <a name="security-warning-dialog"></a>Cuadro de diálogo de advertencia de seguridad

Cuando se usa un ensamblado de proveedor de tipo concreto por primera vez, Visual Studio muestra un cuadro de diálogo de seguridad que le advierte que el proveedor de tipos está a punto de ejecutarse. Antes de Visual Studio carga el proveedor de tipos, ofrece la oportunidad de decidir si confiar en este proveedor determinado. Si confía en el origen del proveedor de tipo, a continuación, seleccione "confiar en este proveedor de tipo". Si no confía en el origen del proveedor de tipo, a continuación, seleccione "no confíe este proveedor de tipo". Confiar en el proveedor le permite ejecutar dentro de Visual Studio y proporcionar IntelliSense y generar características. Pero si el propio proveedor de tipo es malintencionado, ejecuta su código podría poner en peligro el equipo.

Si el proyecto contiene código que hace referencia a los proveedores de tipos que eligió en el cuadro de diálogo no debe confiar en, a continuación, en tiempo de compilación, el compilador notificará un error que indica que el proveedor de tipos no es de confianza. Los tipos que son dependientes en el proveedor de tipos de confianza se indican mediante subrayados ondulados rojos. Es seguro examinar el código en el editor.

Si decide cambiar la configuración de confianza directamente en Visual Studio, realice los pasos siguientes.

### <a name="to-change-the-trust-settings-for-type-providers"></a>Para cambiar la configuración de confianza para los proveedores de tipos

1. En el `Tools` menú, seleccione `Options`y expanda el `F# Tools` nodo.

2. Seleccione `Type Providers`, en la lista de proveedores de tipos, seleccione la casilla de verificación para los proveedores de tipos que confía y desactive la casilla de verificación para aquellos que no confía.

## <a name="see-also"></a>Vea también

- [Proveedores de tipos](index.md)
