---
title: Seguridad del proveedor de tipos
description: 'Obtenga información acerca de la seguridad del proveedor de tipo de F #, incluida la forma de cambiar la configuración de confianza de un proveedor de tipos.'
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: 4f0b55062aec6c560112fe10ca4df77f42493011
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2018
---
# <a name="type-provider-security"></a>Seguridad del proveedor de tipos

Proveedores de tipo son ensamblados (archivos DLL) al que hace referencia el proyecto de F # o el script que contienen código para conectarse a orígenes de datos externos y esta información de tipo de superficie para el entorno de tipo de F #. Por lo general, solo se ejecuta código en los ensamblados que se hace referencia, al compilar y, a continuación, ejecute el código (o en el caso de una secuencia de comandos, envíe el código de F # Interactive). Sin embargo, un ensamblado de proveedor de tipo se ejecutará dentro de Visual Studio cuando simplemente se explora el código en el editor. Esto sucede porque los proveedores de tipo que deba ejecutar para agregar información adicional para el editor, por ejemplo, información rápida sobre herramientas, finalización de IntelliSense y así sucesivamente. Como resultado, hay consideraciones de seguridad adicionales para el tipo de proveedor ensamblados, ya que se ejecutan automáticamente en el proceso de Visual Studio.


## <a name="security-warning-dialog"></a>Cuadro de diálogo de advertencia de seguridad
Cuando se usa un ensamblado de proveedor de tipo concreto por primera vez, Visual Studio muestra un cuadro de diálogo de seguridad que le advierte que el proveedor de tipo está a punto de ejecutarse. Antes de Visual Studio carga el proveedor de tipos, ofrece la oportunidad de decidir si confiar en este proveedor determinado. Si confía en el origen del proveedor de tipo, a continuación, seleccione "confiar en este proveedor de tipo". Si no confía en el origen del proveedor de tipo, a continuación, seleccione "no confiar en este proveedor de tipo." Confiar en el proveedor permite que se ejecuta dentro de Visual Studio y proporcionar IntelliSense y compilar características. Pero si el propio proveedor de tipo es malintencionado, al ejecutar su código pueda poner en peligro el equipo.

Si el proyecto contiene código que hace referencia a proveedores de tipos que eligió en el cuadro de diálogo no confía, a continuación, en tiempo de compilación, el compilador notificará un error que indica que el proveedor de tipos no es de confianza. Los tipos que son depende del proveedor de tipo no es de confianza se indican mediante un subrayado ondulado rojo. Es seguro examinar el código en el editor.

Si decide cambiar la configuración de confianza directamente en Visual Studio, realice los pasos siguientes.


#### <a name="to-change-the-trust-settings-for-type-providers"></a>Para cambiar la configuración de confianza para los proveedores de tipo

1. En el `Tools` menú, seleccione `Options`y expanda el `F# Tools` nodo.
<br />

2. Seleccione `Type Providers`, en la lista de proveedores de tipo, seleccione la casilla de verificación para los proveedores de tipo confía y desactive la casilla de verificación para los que no confías.
<br />


## <a name="see-also"></a>Vea también
[Proveedores de tipos](index.md)
