---
title: Retraso de la firma de un ensamblado
description: En este artículo se describe la firma diferida o parcial, que reserva espacio en el archivo PE para la firma de nombre seguro, pero aplaza la firma real.
ms.date: 08/19/2019
helpviewer_keywords:
- deferring assembly signing
- signing assemblies
- assemblies [.NET Framework], signing
- strong-named assemblies, delaying assembly signing
- partial assembly signing
ms.assetid: 9d300e17-5bf1-4360-97da-2aa55efd9070
dev_langs:
- csharp
- vb
- cpp
ms.openlocfilehash: 7b5c8c8463fdc573782fa457bf5671c72a7e25f7
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/13/2020
ms.locfileid: "83378504"
---
# <a name="delay-sign-an-assembly"></a>Retraso de la firma de un ensamblado

Una organización podría tener un par de claves muy bien guardado al que los desarrolladores no pudieran acceder cada día. La clave pública suele estar disponible, pero el acceso a la clave privada estaría restringido a algunas personas. Al desarrollar ensamblados con nombres seguros, cada ensamblado que hace referencia al ensamblado de destino con nombre seguro contiene el token de la clave pública usada para asignar un nombre seguro al ensamblado de destino. Esto requiere que la clave pública esté disponible durante el proceso de desarrollo.

Puede usar la firma retardada o parcial en tiempo de compilación para reservar espacio en el archivo portable ejecutable (PE) para la firma de nombre seguro, pero retrase la firma real hasta una fase posterior, normalmente, justo antes de enviar el ensamblado.

Para retrasar la firma de un ensamblado:

1. Obtenga la parte de la clave pública del par de claves de la organización que se encargará de la firma. Normalmente, esta clave tiene la forma de un archivo *.snk*, el cual se puede crear mediante la [herramienta de nombre seguro (Sn.exe)](../../framework/tools/sn-exe-strong-name-tool.md) proporcionada por Windows SDK.

2. Se anota el código fuente del ensamblado con dos atributos personalizados de <xref:System.Reflection>:

   - <xref:System.Reflection.AssemblyKeyFileAttribute>, que pasa el nombre del archivo que contiene la clave pública como parámetro a su constructor.

   - <xref:System.Reflection.AssemblyDelaySignAttribute>, que indica que se está retrasando la firma. Para ello, se pasa **true** como parámetro a su constructor.

   Por ejemplo:

   ```cpp
   [assembly:AssemblyKeyFileAttribute("myKey.snk")];
   [assembly:AssemblyDelaySignAttribute(true)];
   ```

   ```csharp
   [assembly:AssemblyKeyFileAttribute("myKey.snk")]
   [assembly:AssemblyDelaySignAttribute(true)]
   ```

   ```vb
   <Assembly:AssemblyKeyFileAttribute("myKey.snk")>
   <Assembly:AssemblyDelaySignAttribute(True)>
   ```

3. El compilador inserta la clave pública en el manifiesto del ensamblado y reserva espacio en el archivo PE para la firma de nombre seguro completo. La clave pública real se debe guardar mientras se compila el ensamblado para que otros ensamblados que hagan referencia a este puedan obtenerla y guardarla en su propia referencia al ensamblado.

4. Dado que el ensamblado no tiene una firma de nombre seguro válida, la comprobación de firma debe estar desactivada. Puede hacerlo mediante la opción **–Vr** con la herramienta de nombre seguro.

     En el ejemplo siguiente se desactiva la comprobación para un ensamblado denominado *myAssembly.dll*.

   ```console
   sn –Vr myAssembly.dll
   ```

   Para desactivar la comprobación en plataformas en las que no se puede ejecutar la herramienta de nombre seguro, como los microprocesadores de Advanced RISC Machine (ARM), use la opción **–Vk** para crear un archivo del Registro. Importe el archivo del Registro en el Registro del equipo en el que quiere desactivar la comprobación. En el ejemplo siguiente se crea un archivo del Registro para `myAssembly.dll`.

   ```console
   sn –Vk myRegFile.reg myAssembly.dll
   ```

   Con la opción **–Vr** o **–Vk**, puede incluir opcionalmente un archivo *.snk* para probar la firma de la clave.

   > [!WARNING]
   > Para garantizar la seguridad, no confíe únicamente en el uso de nombres seguros. Estos solo proporcionan una identidad única.

   > [!NOTE]
   > Si usa la firma retardada durante el desarrollo con Visual Studio en un equipo de 64 bits y compila un ensamblado para **Cualquier CPU**, es posible que deba aplicar la opción **-Vr** dos veces. (En Visual Studio, **Cualquier CPU** es un valor de la propiedad de compilación **Destino de la plataforma**. Cuando se compila desde la línea de comandos, es el valor predeterminado). Para ejecutar la aplicación desde la línea de comandos o desde el Explorador de archivos, use la versión de 64 bits de [Sn.exe (herramienta de nombre seguro)](../../framework/tools/sn-exe-strong-name-tool.md) para aplicar la opción **-Vr** al ensamblado. Para cargar el ensamblado en Visual Studio en tiempo de diseño (por ejemplo, si el ensamblado contiene componentes que usan otros ensamblados de la aplicación), use la versión de 32 bits de la herramienta de nombre seguro. Esto se debe a que el compilador Just-In-Time (JIT) compila el ensamblado en código nativo de 64 bits cuando el ensamblado se ejecuta desde la línea de comandos y en código nativo de 32 bits cuando el ensamblado se carga en el entorno de tiempo de diseño.

5. Después, normalmente justo antes del envío, se envía el ensamblado a la autoridad de firma de la organización para que lleve a cabo la firma de nombre seguro real mediante la opción **–R** con la herramienta de nombre seguro.

   En el ejemplo siguiente se firma un ensamblado denominado *myAssembly.dll* con un nombre seguro mediante el par de claves *sgKey.snk*.

   ```console
   sn -R myAssembly.dll sgKey.snk
   ```

## <a name="see-also"></a>Vea también

- [Creación de ensamblados](create.md)
- [Cómo: Crear un par de claves privada y pública](create-public-private-key-pair.md)
- [Sn.exe (herramienta de nombre seguro)](../../framework/tools/sn-exe-strong-name-tool.md)
