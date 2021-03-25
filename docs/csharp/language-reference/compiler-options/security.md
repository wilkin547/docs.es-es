---
description: Opciones del compilador de C# para la seguridad. Estas opciones controlan la firma de ensamblados o el diseño del espacio de direcciones.
title: 'Opciones del compilador de C#: opciones de seguridad'
ms.date: 03/12/2021
f1_keywords:
- cs.build.options
helpviewer_keywords:
- PublicSign compiler option [C#]
- DelaySign compiler option [C#]
- KeyFile compiler option [C#]
- KeyContainer compiler option [C#]
- HighEntropyVA compiler option [C#]
ms.openlocfilehash: db7b612fa2e4ddb566ac2ba5ef9e4e66c5f0b0ab
ms.sourcegitcommit: 0bb8074d524e0dcf165430b744bb143461f17026
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2021
ms.locfileid: "103482469"
---
# <a name="c-compiler-options-for-security-options"></a>Opciones del compilador de C# para opciones de seguridad

Las opciones siguientes controlan las opciones de seguridad del compilador. La nueva sintaxis de MSBuild se muestra en **negrita**. La sintaxis de *csc.exe* anterior se muestra en `code style`.

- **PublicSign** / `-publicsign`: se firma el ensamblado públicamente.
- **DelaySign** / `-delaysign`: se retrasa la firma del ensamblado usando solo la parte pública de la clave de nombre seguro.
- **KeyFile** / `-keyfile`: se especifica un archivo de clave con nombre seguro.
- **KeyContainer** / `-keycontainer`: se especifica un contenedor de claves con nombre seguro.
- **HighEntropyVA**  /  `-highentropyva`: se habilita la selección aleatoria del diseño del espacio de direcciones (ASLR) de alta entropía.

## <a name="publicsign"></a>PublicSign

Esta opción hace que el compilador aplique una clave pública pero no firma el ensamblado. La opción **PublicSign** también establece un bit en el ensamblado que indica al entorno de ejecución que el archivo está firmado.

```xml
<PublicSign>true</PublicSign>
```

Para la opción **PublicSign** es necesario usar la opción [**KeyFile**](#keyfile) o [**KeyContainer**](#keycontainer). Las opciones **keyFile** y **KeyContainer** especifican la clave pública. Las opciones **PublicSign** y **PublicSign** son mutuamente excluyentes. A veces llamada "firma falsa" o "firma OSS", la firma pública incluye la clave pública en un ensamblado de salida y establece la marca "signed". La firma pública no firma realmente el ensamblado con una clave privada. Los desarrolladores usan el signo público para los proyectos de código abierto.  Los usuarios crean ensamblados que son compatibles con los ensamblados "totalmente firmados" publicados cuando no tienen acceso a la clave privada utilizada para firmar los ensamblados. Como prácticamente ningún consumidor necesita realmente comprobar si el ensamblado está firmado de forma completa, estos ensamblados creados de forma pública se pueden utilizar en casi todos los escenarios en los que se utilizaría el ensamblado totalmente firmado.

## <a name="delaysign"></a>DelaySign

Esta opción hace que el compilador reserve espacio en el archivo de salida de manera que se pueda agregar una firma digital más adelante.

```xml
<DelaySign>true</DelaySign>
```

Use **DelaySign-** si quiere un ensamblado completamente firmado. Use **DelaySign** si solo quiere incluir la clave pública en el ensamblado. La opción **DelaySign** no tiene ningún efecto a menos que se use con [**KeyFile**](#keyfile) o [**KeyContainer**](#keycontainer). Las opciones [**KeyContainer**](#keycontainer) y [**PublicSign**](#publicsign) son mutuamente excluyentes. Cuando se solicita un ensamblado totalmente firmado, el compilador genera un valor hash para el archivo que contiene el manifiesto (metadatos del ensamblado) y firma dicho valor mediante la clave privada. Esta operación crea una firma digital que se almacena en el archivo que contiene el manifiesto. Cuando se retrasa la firma de un ensamblado, el compilador no procesa ni almacena la firma. En su lugar, reserva espacio en el archivo para que la firma se pueda agregar después.

El uso de **DelaySign** permite a un evaluador colocar el ensamblado en la caché global. Después de realizar las pruebas, coloque la clave privada en el ensamblado mediante la utilidad [Assembly Linker](../../../framework/tools/al-exe-assembly-linker.md) para firmar el ensamblado por completo. Para obtener más información, vea [Crear y usar ensamblados con nombre seguro](../../../standard/assembly/create-use-strong-named.md) y [Retraso de la firma de un ensamblado](../../../standard/assembly/delay-sign.md).

## <a name="keyfile"></a>KeyFile

Especifica el nombre de archivo que contiene la clave criptográfica.

```xml
<KeyFile>filename</KeyFile>
```

`file` es el nombre del archivo que contiene la clave de nombre seguro. Cuando se usa esta opción, el compilador inserta la clave pública del archivo especificado en el manifiesto del ensamblado y, después, firma el último ensamblado con la clave privada. Para generar un archivo de claves, escriba `sn -k file` en la línea de comandos. Si se compila con [ **-target:module**](output.md#targettype), el nombre del archivo de claves se mantiene en el módulo y se incorpora en el ensamblado que se crea al compilarlo con [**AddModules**](inputs.md#addmodules). También puede pasar la información de cifrado al compilador con [**Keycontainer**](#keycontainer). Use [**DelaySign**](#delaysign) si quiere firmar el ensamblado de forma parcial. Si se especifica tanto **KeyFile** como **KeyContainer** en la misma compilación, el compilador probará primero el contenedor de claves. Si lo consigue, el ensamblado se firma con la información del contenedor de claves. Si el compilador no encuentra el contenedor de claves, probará el archivo especificado con [**KeyFile**](#keyfile). Si la operación es correcta, el ensamblado se firma con la información del archivo de clave y la información de la clave se instalará en el contenedor de claves. En la siguiente compilación, el contenedor de claves será válido. Es posible que un archivo de clave solo contenga la clave pública. Para obtener más información, vea [Crear y usar ensamblados con nombre seguro](../../../standard/assembly/create-use-strong-named.md) y [Retraso de la firma de un ensamblado](../../../standard/assembly/delay-sign.md).

## <a name="keycontainer"></a>KeyContainer

Especifica el nombre del contenedor de claves criptográficas.

```xml
<KeyContainer>container</KeyContainer>
```

`container` es el nombre del contenedor de claves de nombre seguro. Cuando se usa la opción **KeyContainer**, el compilador crea un componente que se puede compartir. El compilador inserta una clave pública del contenedor especificado en el manifiesto del ensamblado y firma el último ensamblado con la clave privada. Para generar un archivo de claves, escriba `sn -k file` en la línea de comandos. `sn -i` instala el par de claves en un contenedor. Esta opción no se admite cuando el compilador se ejecuta en CoreCLR. Para firmar un ensamblado al compilar en CoreCLR, use la opción [**KeyFile**](#keyfile). Si realiza la compilación con [**TargetType**](output.md#targettype), el nombre del archivo de claves se mantiene en el módulo y se incorpora al ensamblado al compilar este módulo en un ensamblado con [**AddModules**](inputs.md#addmodules). También se puede especificar esta opción como un atributo personalizado (<xref:System.Reflection.AssemblyKeyNameAttribute?displayProperty=nameWithType>) en el código fuente de cualquier módulo del Lenguaje Intermedio de Microsoft (MSIL). También se puede pasar la información de cifrado al compilador con [**KeyFile**](#keyfile). Use [**DelaySign**](#delaysign) para agregar la clave pública al manifiesto del ensamblado pero firmarlo cuando se haya probado. Para obtener más información, vea [Crear y usar ensamblados con nombre seguro](../../../standard/assembly/create-use-strong-named.md) y [Retraso de la firma de un ensamblado](../../../standard/assembly/delay-sign.md).

## <a name="highentropyva"></a>HighEntropyVA

La opción del compilador **HighEntropyVA** indica al kernel de Windows si un archivo ejecutable determinado admite la selección aleatoria del diseño del espacio de direcciones (ASLR) de alta entropía.

```xml
<HighEntropyVA>true</HighEntropyVA>
```

Esta opción especifica que un archivo ejecutable de 64 bits o un archivo ejecutable marcado con la opción del compilador [**PlatformTarget**](output.md#platformtarget) admite un espacio de direcciones virtuales de alta entropía. La opción está deshabilitada de forma predeterminada. Use **HighEntropyVA** para habilitarla.

La opción **HighEntropyVA** habilita las versiones compatibles del kernel de Windows para usar niveles superiores de entropía al aleatorizar el diseño del espacio de direcciones de un proceso como parte de ASLR. El uso de niveles superiores de entropía significa que un mayor número de direcciones se puede asignar a las regiones de memoria como pilas y montones. Como resultado, la ubicación de un área de memoria concreta es más difícil de adivinar. La opción del compilador **HighEntropyVA** necesita que el archivo ejecutable de destino y todos los módulos de los que depende puedan controlar los valores de puntero superiores a 4 gigabytes (GB), cuando se ejecutan como un proceso de 64 bits.
