---
title: Elegir .NET Framework 2.0 en Windows 8 como versión de destino
description: 'Obtenga información acerca de la versión anterior de .NET Framework de destino cuando se usa F #.'
ms.date: 05/16/2016
ms.openlocfilehash: 9b08cced63b46778a5081d4de710991a6299fd29
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="targeting-older-versions-of-net"></a>Selección de destino para versiones anteriores de .NET

> [!NOTE]
En este artículo no está actualizado con el más reciente de Visual Studio.  Se va a actualizar.

El siguiente error puede aparecer si intentas tener como destino .NET Framework 2.0, 3.0 o 3.5 en F # del proyecto cuando se instala Visual Studio en Windows 8.1: 

```
This project requires the 2.0 F# runtime, but that runtime is not installed.
```

Este error se sabe que se producen en la combinación de las condiciones siguiente:


- Ha instalado Visual Studio en Windows 8.1.
<br />

- No habilite .NET Framework 3.5 antes de instalar Visual Studio.
<br />

- El proyecto tiene como destino .NET Framework 2.0, 3.0 o 3.5.
<br />

Cuando se instala Visual Studio, que detecta las versiones instaladas de .NET Framework e instala el Runtime de F # 2.0 sólo si .NET Framework 3.5 está instalado y habilitado.


## <a name="resolving-the-error"></a>Resolver el Error
Para resolver este error, puede que ya sea una versión más reciente de .NET Framework de destino, o puede habilitar .NET Framework 3.5 en Windows 8.1 y, a continuación, instalar el runtime de F # 2.0 ejecutando el programa de instalación de Visual Studio con la **reparación** opción.


#### <a name="to-enable-the-net-framework-35-on-windows-81"></a>Para habilitar .NET Framework 3.5 en Windows 8.1

1. En el **iniciar** pantalla, empieza a escribir **el Panel de Control**.
<br />  A medida que escribe ese nombre, la **el Panel de Control** icono aparece bajo la **aplicaciones** encabezado.
<br />

2. Elija la **el Panel de Control** icono, elija la **programas** icono y, a continuación, elija la **o desactivar las características de Windows Active** vínculo.
<br />

3. Asegúrese de que el **.NET Framework 3.5 (incluye .NET 2.0 y 3.0)** casilla de verificación está seleccionada y, a continuación, elija la **Aceptar** botón.
<br />  No es necesario seleccionar las casillas de verificación para todos los nodos secundarios para los componentes opcionales de .NET Framework.
<br />  .NET Framework 3.5 está habilitada si no estaba inicializada.
<br />


#### <a name="to-install-the-f-20-runtime"></a>Para instalar el runtime de F # 2.0

1. En el Panel de Control, elija la **programas** vincular y, a continuación, elija la **programas y características** vínculo.
<br />

2. En la lista de programas instalados, elija la edición de Visual Studio que ha instalado y, a continuación, elija la **cambio** botón.
<br />

3. Cuando se inicia el programa de instalación, elija la **reparación** botón.
<br />  Para obtener más información, consulte [instalar Visual Studio](https://msdn.microsoft.com/library/e2h7fzkw.aspx).
<br />
## <a name="see-also"></a>Vea también
[Visual F#](../index.md)
