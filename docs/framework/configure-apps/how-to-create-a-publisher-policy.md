---
title: Procedimiento para crear una directiva de publicador
ms.date: 03/30/2017
helpviewer_keywords:
- publisher policy assembly
- publisher policy files
- GAC (global assembly cache), publisher policy assembly
- global assembly cache, publisher policy assembly
ms.assetid: 8046bc5d-2fa9-4277-8a5e-6dcc96c281d9
ms.openlocfilehash: 7c36f6126f0d779a43a22fc11e647ba2d3b03a30
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/20/2020
ms.locfileid: "81646055"
---
# <a name="how-to-create-a-publisher-policy"></a>Procedimiento para crear una directiva de publicador

Los proveedores de ensamblados pueden indicar que las aplicaciones deben usar una versión más reciente de un ensamblado mediante la inclusión de un archivo de directiva de publicador con el ensamblado actualizado. El archivo de directiva de publicador especifica la redirección de ensamblados y la configuración de base de código, y utiliza el mismo formato que un archivo de configuración de la aplicación. El archivo de directiva de publicador se compila en un ensamblado y se coloca en la caché global de ensamblados.

Hay tres pasos implicados en la creación de una directiva de publicador:

1. Cree un archivo de directiva de publicador.

2. Cree un ensamblado de directiva de publicador.

3. Agregue el ensamblado de directiva de publicador a la caché global de ensamblados.

El esquema para la directiva de publicador se describe en Redirección de [versiones](redirect-assembly-versions.md)de ensamblado . En el ejemplo siguiente se muestra un `myAssembly` archivo de directiva de publicador que redirige una versión a otra.

```xml
<configuration>
   <runtime>
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">
       <dependentAssembly>
         <assemblyIdentity name="myAssembly"
                           publicKeyToken="32ab4ba45e0a69a1"
                           culture="en-us" />
         <!-- Redirecting to version 2.0.0.0 of the assembly. -->
         <bindingRedirect oldVersion="1.0.0.0"
                          newVersion="2.0.0.0"/>
       </dependentAssembly>
      </assemblyBinding>
   </runtime>
</configuration>
```

Para obtener información sobre cómo especificar una base de código, consulte [Especificación](specify-assembly-location.md)de la ubicación de un ensamblado .

## <a name="creating-the-publisher-policy-assembly"></a>Creación del ensamblado de directivas de publicador

Use el vinculador de [ensamblados (Al.exe)](../tools/al-exe-assembly-linker.md) para crear el ensamblado de directiva de publicador.

#### <a name="to-create-a-publisher-policy-assembly"></a>Para crear un ensamblado de directiva de publicador

Escriba el siguiente comando en el símbolo del sistema:

```console
al /link:publisherPolicyFile /out:publisherPolicyAssemblyFile /keyfile:keyPairFile /platform:processorArchitecture
```

En este comando:

- El `publisherPolicyFile` argumento es el nombre del archivo de directiva del publicador.

- El `publisherPolicyAssemblyFile` argumento es el nombre del ensamblado de directiva de publicador que resulta de este comando. El nombre del archivo de ensamblado debe seguir el formato:

  'policy.majorNumber.minorNumber.mainAssemblyName.dll'

- El `keyPairFile` argumento es el nombre del archivo que contiene el par de claves. Debe firmar el ensamblado y el ensamblado de directiva de publicador con el mismo par de claves.

- El `processorArchitecture` argumento identifica la plataforma de destino de un ensamblado específico del procesador.

  > [!NOTE]
  > La capacidad de dirigirse a una arquitectura de procesador específica está disponible a partir de .NET Framework 2.0.

La capacidad de dirigirse a una arquitectura de procesador específica está disponible a partir de .NET Framework 2.0. El siguiente comando crea un `policy.1.0.myAssembly` ensamblado de directiva `pub.config`de publicador al que se llama desde `sgKey.snk` un archivo de directiva de publicador denominado , asigna un nombre seguro al ensamblado mediante el par de claves del archivo y especifica que el ensamblado tiene como destino la arquitectura del procesador x86.

```console
al /link:pub.config /out:policy.1.0.myAssembly.dll /keyfile:sgKey.snk /platform:x86
```

El ensamblado de directiva de publicador debe coincidir con la arquitectura de procesador del ensamblado al que se aplica. Por lo tanto, <xref:System.Reflection.AssemblyName.ProcessorArchitecture%2A> si <xref:System.Reflection.ProcessorArchitecture.MSIL>el ensamblado tiene un valor de `/platform:anycpu`, el ensamblado de directiva de publicador para ese ensamblado debe crearse con . Debe proporcionar un ensamblado de directiva de publicador independiente para cada ensamblado específico del procesador.

Una consecuencia de esta regla es que para cambiar la arquitectura del procesador para un ensamblado, debe cambiar el componente principal o secundario del número de versión, de modo que pueda proporcionar un nuevo ensamblado de directiva de publicador con la arquitectura de procesador correcta. El ensamblado de directiva de publicador anterior no puede reparar el ensamblado una vez que el ensamblado tiene una arquitectura de procesador diferente.

Otra consecuencia es que el vinculador de la versión 2.0 no se puede usar para crear un ensamblado de directiva de publicador para un ensamblado compilado con versiones anteriores de .NET Framework, porque siempre especifica la arquitectura del procesador.

## <a name="adding-the-publisher-policy-assembly-to-the-global-assembly-cache"></a>Agregar el ensamblado de directivas de publicador a la caché global de ensamblados

Utilice la herramienta Caché global de [ensamblados (Gacutil.exe)](../tools/gacutil-exe-gac-tool.md) para agregar el ensamblado de directiva de publicador a la caché global de ensamblados.

### <a name="to-add-the-publisher-policy-assembly-to-the-global-assembly-cache"></a>Para agregar el ensamblado de directiva de publicador a la caché global de ensamblados

Escriba el siguiente comando en el símbolo del sistema:

```console
gacutil /i publisherPolicyAssemblyFile
```

El siguiente comando `policy.1.0.myAssembly.dll` se agrega a la caché global de ensamblados.

```console
gacutil /i policy.1.0.myAssembly.dll
```

> [!IMPORTANT]
> El ensamblado de directiva de publicador no se puede agregar a `/link` la caché global de ensamblados a menos que el archivo de directiva de publicador original especificado en el argumento se encuentre en el mismo directorio que el ensamblado.

## <a name="see-also"></a>Consulte también

- [Programar con ensamblados](../../standard/assembly/index.md)
- [Cómo el motor en tiempo de ejecución localiza ensamblados](../deployment/how-the-runtime-locates-assemblies.md)
- [Configurar aplicaciones con archivos de configuración](index.md)
- [Esquema de la configuración de Common Language Runtime](./file-schema/runtime/index.md)
- [Esquema de los archivos de configuración](./file-schema/index.md)
- [Redirigir versiones de ensamblado](redirect-assembly-versions.md)
