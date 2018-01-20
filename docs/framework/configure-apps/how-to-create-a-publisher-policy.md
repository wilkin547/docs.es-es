---
title: "Cómo: Crear una directiva de publicador"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- publisher policy assembly
- publisher policy files
- GAC (global assembly cache), publisher policy assembly
- global assembly cache, publisher policy assembly
ms.assetid: 8046bc5d-2fa9-4277-8a5e-6dcc96c281d9
caps.latest.revision: "15"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: 4ccd490f6d31ad1d20128497e5115147eddb3df4
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-create-a-publisher-policy"></a>Cómo: Crear una directiva de publicador
Los proveedores de ensamblados pueden indicar que las aplicaciones deben usar una versión más reciente de un ensamblado mediante la inclusión de un archivo de directiva de publicador con el ensamblado actualizado. El archivo de directiva de publicador especifica la redirección de ensamblado y la configuración del código base y usa el mismo formato que un archivo de configuración de aplicación. El archivo de directiva de edición se compila en un ensamblado y se coloca en la caché global de ensamblados.  
  
 Hay tres pasos necesarios para crear una directiva de edición:  
  
1.  Crear un archivo de directiva de edición.  
  
2.  Crear un ensamblado de directivas del Editor.  
  
3.  Agregue el ensamblado de directivas de publicador a la caché global de ensamblados.  
  
 Se describe el esquema de directiva de publicador en [redirigir versiones de ensamblado](../../../docs/framework/configure-apps/redirect-assembly-versions.md). En el ejemplo siguiente se muestra un editor de archivo de directiva que redirige una versión de `myAssembly` a otro.  
  
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
  
 Para obtener información sobre cómo especificar un código base, vea [especificar la ubicación de un ensamblado](../../../docs/framework/configure-apps/specify-assembly-location.md).  
  
## <a name="creating-the-publisher-policy-assembly"></a>Crear el ensamblado de directiva de publicador  
 Use la [Assembly Linker (Al.exe)](../../../docs/framework/tools/al-exe-assembly-linker.md) para crear el ensamblado de directivas de publicador.  
  
#### <a name="to-create-a-publisher-policy-assembly"></a>Para crear un ensamblado de directivas de publicador  
  
1.  Escriba el siguiente comando en el símbolo del sistema:  
  
     **al /link:** *publisherPolicyFile* **/out:** *publisherPolicyAssemblyFile* **/keyfile:** *keyPairFile* **/platform:** *processorArchitecture*  
  
     En este comando:  
  
    -   El *directivas* argumento es el nombre del archivo de directiva de publicador.  
  
    -   El *publisherPolicyAssemblyFile* argumento es el nombre del ensamblado de directiva de publicador que da como resultado de este comando. El nombre de archivo de ensamblado debe seguir el formato:  
  
         **Directiva.** *majorNumber* **.** *número secundario* **.** *nombre de ensamblado principal* **.dll**  
  
    -   El *keyPairFile* argumento es el nombre del archivo que contiene el par de claves. Debe firmar el ensamblado y el ensamblado de directivas del publicador con el mismo par de claves.  
  
    -   El *processorArchitecture* argumento identifica la plataforma de destino de un ensamblado específico del procesador.  
  
        > [!NOTE]
        >  La capacidad de tener como destino una arquitectura de procesador específico es nueva en la versión 2.0 de .NET Framework.  
  
     El siguiente comando crea un ensamblado de directivas del editor denominado `policy.1.0.myAssembly` desde un archivo de directiva de publicador llama `pub.config`, asigna un nombre seguro al ensamblado mediante el par de claves en el `sgKey.snk` de archivos y especifica que el ensamblado tiene como destino el x86 arquitectura de procesador.  
  
    ```  
    al /link:pub.config /out:policy.1.0.myAssembly.dll /keyfile:sgKey.snk /platform:x86  
    ```  
  
     El ensamblado de directivas del editor debe coincidir con la arquitectura del procesador del ensamblado que se aplica. Por lo tanto, si el ensamblado tiene un <xref:System.Reflection.AssemblyName.ProcessorArchitecture%2A> valo <xref:System.Reflection.ProcessorArchitecture.MSIL>, el ensamblado de directivas de publicador para ese ensamblado debe crearse con `/platform:anycpu`. Debe proporcionar otro ensamblado de directivas de publicador para cada ensamblado específico del procesador.  
  
     Una consecuencia de esta regla es que, con el fin de cambiar la arquitectura de procesador para un ensamblado, debe cambiar el componente principal o secundario del número de versión, por lo que puede proporcionar un nuevo ensamblado de directiva de publicador con la arquitectura correcta del procesador. El ensamblado de directivas de publicador anterior no puede reparar el ensamblado una vez que el ensamblado tiene una arquitectura de procesador distinta.  
  
     Otra consecuencia es que no se puede usar la versión 2.0 del vinculador para crear un ensamblado de directivas de publicador para un ensamblado compilado con versiones anteriores de .NET Framework, porque siempre especifica la arquitectura del procesador.  
  
## <a name="adding-the-publisher-policy-assembly-to-the-global-assembly-cache"></a>Agregar el ensamblado de directivas de publicador a la caché Global de ensamblados  
 Use la [herramienta caché Global de ensamblados (Gacutil.exe)](../../../docs/framework/tools/gacutil-exe-gac-tool.md) para agregar el ensamblado de directivas de publicador a la caché global de ensamblados.  
  
#### <a name="to-add-the-publisher-policy-assembly-to-the-global-assembly-cache"></a>Para agregar el ensamblado de directivas de publicador a la caché global de ensamblados  
  
1.  Escriba el siguiente comando en el símbolo del sistema:  
  
     **gacutil /i**  *publisherPolicyAssemblyFile*  
  
     El comando siguiente agrega `policy.1.0.myAssembly.dll` a la caché global de ensamblados.  
  
    ```  
    gacutil /i policy.1.0.myAssembly.dll  
    ```  
  
    > [!IMPORTANT]
    >  No se puede agregar el ensamblado de directivas de publicador a la caché de ensamblados global, a menos que el archivo de directiva de publicador original se encuentra en el mismo directorio que el ensamblado.  
  
## <a name="see-also"></a>Vea también  
 [Programar con ensamblados](../../../docs/framework/app-domains/programming-with-assemblies.md)  
 [Cómo el motor en tiempo de ejecución ubica ensamblados](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)  
 [Configurar aplicaciones](../../../docs/framework/configure-apps/index.md)  
 [Configurar aplicaciones de .NET Framework](http://msdn.microsoft.com/library/d789b592-fcb5-4e3d-8ac9-e0299adaaa42)  
 [Esquema de la configuración de Common Language Runtime](../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [Esquema de los archivos de configuración](../../../docs/framework/configure-apps/file-schema/index.md)  
 [Redirigir versiones de ensamblado](../../../docs/framework/configure-apps/redirect-assembly-versions.md)
