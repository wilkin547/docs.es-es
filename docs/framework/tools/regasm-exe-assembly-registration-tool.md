---
title: Regasm.exe (Herramienta de registro de ensamblados)
ms.date: 03/30/2017
helpviewer_keywords:
- Assembly Registration tool
- assemblies [.NET Framework], registering
- Regasm.exe
- registering assemblies
ms.assetid: e190e342-36ef-4651-a0b4-0e8c2c0281cb
ms.openlocfilehash: 45b4c6c08d3afb948444a8c97dc32bd41f2615ce
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "73104950"
---
# <a name="regasmexe-assembly-registration-tool"></a>Regasm.exe (Herramienta de registro de ensamblados)

La herramienta de registro de ensamblados lee los metadatos de un ensamblado y agrega las entradas necesarias al Registro, lo que permite a los clientes COM crear clases de .NET Framework de forma transparente. Una vez registrada una clase, cualquier cliente COM puede usarla como si se tratase de una clase COM. La clase se registra una sola vez, cuando se instala el ensamblado. Las instancias de las clases del ensamblado no se pueden crear a partir de COM si no están registradas.

Para ejecutar la herramienta, use el Símbolo del sistema para desarrolladores de Visual Studio. Para más información, consulte [Símbolos del sistema](developer-command-prompt-for-vs.md).

En el símbolo del sistema, escriba lo siguiente:

## <a name="syntax"></a>Sintaxis

```console
regasm assemblyFile [options]
```

## <a name="parameters"></a>Parámetros

|Parámetro|Descripción|
|---------------|-----------------|
|*assemblyFile*|El ensamblado que se va a registrar con COM.|

|Opción|Descripción|
|------------|-----------------|
|**/codebase**|Crea una entrada de código base en el Registro. La entrada de código base especifica la ruta de acceso de archivo de un ensamblado que no está instalado en la caché global de ensamblados. No debe especificar esta opción si posteriormente va a instalar el ensamblado que va a registrar en la caché global de ensamblados. El argumento *assemblyFile* especificado con la opción **/codebase** debe ser un [ensamblado con nombre seguro](../../standard/assembly/strong-named.md).|
|**/registered**|Especifica que esta herramienta solo hará referencia a las bibliotecas de tipos que ya se hayan registrado.|
|**/asmpath:directory**|Especifica un directorio que contiene las referencias de ensamblado. Se debe usar con la opción **/regfile**.|
|**/nologo**|Suprime la presentación de la portada de inicio de Microsoft.|
|**/regfile** [ **:** *regFile*]|Genera el archivo .reg especificado para el ensamblado, que contiene las entradas del Registro necesarias. El hecho de especificar esta opción no cambia el Registro. No se puede usar esta opción con las opciones **/u** o **/tlb**.|
|**/silent** o **/s**|Suprime la presentación de mensajes de aprobación.|
|**/tlb** [ **:** *typeLibFile*]|Genera una biblioteca de tipos a partir del ensamblado especificado que contiene definiciones de los tipos accesibles definidos en el ensamblado.|
|**/unregister** o **/u**|Anula el registro de las clases que se pueden crear que se encuentran en *assemblyFile*. Cuando se omite esta opción, Regasm.exe registra en el ensamblado las clases que se pueden crear.|
|**/verbose**|Especifica el modo detallado; cuando se especifica con la opción **/tlb**, muestra una lista de los ensamblados a los que se hace referencia para los que es necesario generar una biblioteca de tipos.|
|**/?** o **/help**|Muestra las opciones y la sintaxis de los comandos para la herramienta.|

> [!NOTE]
> Las opciones de la línea de comandos de Regasm.exe no distinguen entre mayúsculas y minúsculas. Por otra parte, basta con proporcionar parte de la opción de forma que se identifique de manera inequívoca. Por ejemplo, **/n** equivale a **/nologo** y **/t:** *outfile.tlb*, a **/tlb:** *outfile.tlb*.

## <a name="remarks"></a>Comentarios

Puede usar la opción **/regfile** para generar un archivo .reg que contenga las entradas del Registro en lugar de hacer los cambios en el Registro directamente. El Registro se puede actualizar en un equipo importando el archivo .reg con la herramienta Editor del Registro (Regedit.exe). Tenga en cuenta que el archivo .reg no contiene actualizaciones del Registro que se puedan realizar mediante funciones de registro definidas por el usuario.  Tenga en cuenta que la opción **/regfile** solo emite entradas del Registro para clases administradas.  Esta opción no emite entradas del Registro para `TypeLibID` ni `InterfaceID`.

Cuando se especifica la opción **/tlb**, Regasm.exe genera y registra una biblioteca de tipos donde se describen los tipos encontrados en el ensamblado. Regasm.exe coloca las bibliotecas de tipos generadas en el directorio de trabajo actual o en el directorio especificado para el archivo de salida. La generación de una biblioteca de tipos para un ensamblado que hace referencia a otros ensamblados puede provocar la generación de varias bibliotecas de tipos a la vez. Puede usar la biblioteca de tipos para proporcionar información de tipos para las herramientas de desarrollo como Visual Studio. No se debe usar la opción **/tlb** si el ensamblado que se va a registrar lo ha generado la herramienta Importador de la biblioteca de tipos ([Tlbimp.exe](tlbimp-exe-type-library-importer.md)). No se puede exportar una biblioteca de tipos de un ensamblado que se ha importado desde una biblioteca de tipos. El uso de la opción **/tlb** tiene el mismo efecto que el uso de las herramientas Exportador de la biblioteca de tipos ([Tlbexp.exe](tlbexp-exe-type-library-exporter.md)) y Regasm.exe, con la particularidad de que Tlbexp.exe no registra la biblioteca de tipos que genera.  Si usa la opción **/tlb** para registrar una biblioteca de tipos, puede usar la opción **/tlb** con la opción **/unregister** para anular el registro de la biblioteca de tipos. El uso de las dos opciones juntas anulará el registro de la biblioteca de tipos y de las entradas de la interfaz, lo que puede limpiar considerablemente el Registro.

Al registrar un ensamblado para que lo use COM, Regasm.exe agrega entradas al Registro del equipo local. Más concretamente, crea claves del Registro dependientes de la versión que permiten que varias versiones del mismo ensamblado se ejecuten en paralelo en un equipo. Al registrar un ensamblado por primera vez, se crea una clave de nivel superior para el ensamblado y una subclave única para la versión específica. Cada vez que se registra una nueva versión del ensamblado, Regasm.exe crea una subclave para la nueva versión.

Por ejemplo, imagine un escenario en el que registra el componente administrado myComp.dll, versión 1.0.0.0, para que lo use COM. Posteriormente, registra myComp.dll, versión 2.0.0.0. Determina que todas las aplicaciones de cliente COM del equipo están usando myComp.dll versión 2.0.0.0 y decide anular el registro de myComponent.dll versión 1.0.0.0. Este esquema del Registro permite anular el registro de myComp.dll versión 1.0.0.0 porque solo se quita la subclave de la versión 1.0.0.0.

Después de registrar un ensamblado mediante Regasm.exe, puede instalarlo en la [caché global de ensamblados](../app-domains/gac.md) para que se pueda activar desde cualquier cliente COM. Si el ensamblado solo va a activar una única una aplicación, se puede colocar en el directorio de dicha aplicación.

## <a name="examples"></a>Ejemplos

El comando siguiente registra todas las clases públicas contenidas en `myTest.dll`.

```console
regasm myTest.dll
```

El comando siguiente genera el archivo `myTest.reg`, que contiene todas las entradas del Registro necesarias. Este comando no actualiza el Registro.

```console
regasm myTest.dll /regfile:myTest.reg
```

El comando siguiente registra todas las clases públicas contenidas en `myTest.dll`, y genera y registra la biblioteca de tipos `myTest.tlb`, que contiene definiciones de todos los tipos públicos definidos en `myTest.dll`.

```console
regasm myTest.dll /tlb:myTest.tlb
```

## <a name="see-also"></a>Vea también

- [Herramientas](index.md)
- [Tlbexp.exe (Exportador de la biblioteca de tipos)](tlbexp-exe-type-library-exporter.md)
- [TlbImp.exe (Importador de la biblioteca de tipos)](tlbimp-exe-type-library-importer.md)
- [Registrar ensamblados con COM](../interop/registering-assemblies-with-com.md)
- [Símbolos del sistema](developer-command-prompt-for-vs.md)
