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
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "81646055"
---
# <a name="how-to-create-a-publisher-policy"></a>Procedimiento para crear una directiva de publicador

Los proveedores de ensamblados pueden indicar que las aplicaciones deben usar una versión más reciente de un ensamblado mediante la inclusión de un archivo de directiva de edición con el ensamblado actualizado. El archivo de directiva de edición especifica la redirección de ensamblados y la configuración de base de código, y usa el mismo formato que un archivo de configuración de aplicación. El archivo de directiva de edición se compila en un ensamblado y se coloca en la caché global de ensamblados.

Hay tres pasos implicados en la creación de una directiva de edición:

1. Cree un archivo de directiva de edición.

2. Cree un ensamblado de directiva de edición.

3. Agregue el ensamblado de directiva de edición a la caché global de ensamblados.

El esquema de la Directiva de edición se describe en [redirigir versiones de ensamblado](redirect-assembly-versions.md). En el ejemplo siguiente se muestra un archivo de directiva de edición que redirige una versión de `myAssembly` a otra.

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

Para obtener información sobre cómo especificar una base de código, vea [especificar la ubicación de un ensamblado](specify-assembly-location.md).

## <a name="creating-the-publisher-policy-assembly"></a>Crear el ensamblado de directiva de edición

Use [Assembly Linker (al. exe)](../tools/al-exe-assembly-linker.md) para crear el ensamblado de directiva de edición.

#### <a name="to-create-a-publisher-policy-assembly"></a>Para crear un ensamblado de directiva de edición

Escriba el siguiente comando en el símbolo del sistema:

```console
al /link:publisherPolicyFile /out:publisherPolicyAssemblyFile /keyfile:keyPairFile /platform:processorArchitecture
```

En este comando:

- El `publisherPolicyFile` argumento es el nombre del archivo de directiva de edición.

- El `publisherPolicyAssemblyFile` argumento es el nombre del ensamblado de directiva de edición que es el resultado de este comando. El nombre del archivo de ensamblado debe seguir el formato:

  ' Policy. majorNumber. minorNumber. mainAssemblyName. dll '

- El `keyPairFile` argumento es el nombre del archivo que contiene el par de claves. Debe firmar el ensamblado y el ensamblado de directiva de edición con el mismo par de claves.

- El `processorArchitecture` argumento identifica la plataforma de destino de un ensamblado específico del procesador.

  > [!NOTE]
  > La capacidad de dirigirse a una arquitectura de procesador específica está disponible a partir de .NET Framework 2,0.

La capacidad de dirigirse a una arquitectura de procesador específica está disponible a partir de .NET Framework 2,0. El siguiente comando crea un ensamblado de directiva `policy.1.0.myAssembly` de edición llamado desde un archivo de directiva de edición denominado `pub.config` , asigna un nombre seguro al ensamblado mediante el par de claves del `sgKey.snk` archivo y especifica que el ensamblado tiene como destino la arquitectura de procesador x86.

```console
al /link:pub.config /out:policy.1.0.myAssembly.dll /keyfile:sgKey.snk /platform:x86
```

El ensamblado de directiva de edición debe coincidir con la arquitectura del procesador del ensamblado al que se aplica. Por lo tanto, si el ensamblado tiene un <xref:System.Reflection.AssemblyName.ProcessorArchitecture%2A> valor de <xref:System.Reflection.ProcessorArchitecture.MSIL> , el ensamblado de directiva de edición para ese ensamblado debe crearse con `/platform:anycpu` . Debe proporcionar un ensamblado de directiva de edición independiente para cada ensamblado específico del procesador.

Una consecuencia de esta regla es que para cambiar la arquitectura del procesador de un ensamblado, debe cambiar el componente principal o secundario del número de versión, para que pueda proporcionar un nuevo ensamblado de directiva de edición con la arquitectura de procesador correcta. El ensamblado de directiva de edición anterior no puede atender el ensamblado cuando el ensamblado tiene una arquitectura de procesador diferente.

Otra consecuencia es que el enlazador de la versión 2,0 no se puede usar para crear un ensamblado de directiva de edición para un ensamblado compilado con versiones anteriores del .NET Framework, porque siempre especifica la arquitectura del procesador.

## <a name="adding-the-publisher-policy-assembly-to-the-global-assembly-cache"></a>Agregar el ensamblado de directiva de edición a la caché global de ensamblados

Use la [herramienta caché global de ensamblados (Gacutil. exe)](../tools/gacutil-exe-gac-tool.md) para agregar el ensamblado de directiva de edición a la caché global de ensamblados.

### <a name="to-add-the-publisher-policy-assembly-to-the-global-assembly-cache"></a>Para agregar el ensamblado de directiva de edición a la caché global de ensamblados

Escriba el siguiente comando en el símbolo del sistema:

```console
gacutil /i publisherPolicyAssemblyFile
```

El comando siguiente agrega `policy.1.0.myAssembly.dll` a la caché global de ensamblados.

```console
gacutil /i policy.1.0.myAssembly.dll
```

> [!IMPORTANT]
> El ensamblado de directiva de edición no se puede Agregar a la caché global de ensamblados a menos que el archivo de directiva de edición original especificado en el `/link` argumento se encuentre en el mismo directorio que el ensamblado.

## <a name="see-also"></a>Vea también

- [Programar con ensamblados](../../standard/assembly/index.md)
- [Cómo el motor en tiempo de ejecución ubica ensamblados](../deployment/how-the-runtime-locates-assemblies.md)
- [Configurar aplicaciones con archivos de configuración](index.md)
- [Esquema de la configuración de Common Language Runtime](./file-schema/runtime/index.md)
- [Esquema de los archivos de configuración](./file-schema/index.md)
- [Redirigir versiones de ensamblado](redirect-assembly-versions.md)
