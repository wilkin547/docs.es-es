---
title: 'Cómo: Crear una directiva de publicador'
ms.date: 03/30/2017
helpviewer_keywords:
- publisher policy assembly
- publisher policy files
- GAC (global assembly cache), publisher policy assembly
- global assembly cache, publisher policy assembly
ms.assetid: 8046bc5d-2fa9-4277-8a5e-6dcc96c281d9
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 3fdc3786be3307e8c882a33b5139ee34344733b8
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/01/2018
ms.locfileid: "43404415"
---
# <a name="how-to-create-a-publisher-policy"></a>Cómo: Crear una directiva de publicador
Los proveedores de ensamblados pueden indicar que las aplicaciones deben usar una versión más reciente de un ensamblado mediante la inclusión de un archivo de directiva de publicador con el ensamblado actualizado. El archivo de directiva de publicador especifica redirección de ensamblado y la configuración de base de código y usa el mismo formato que un archivo de configuración de la aplicación. El archivo de directiva de publicador se compila en un ensamblado y colocar en la caché global de ensamblados.  
  
 Hay tres pasos implicados en la creación de una directiva de publicador:  
  
1.  Cree un archivo de directiva de publicador.  
  
2.  Crear un ensamblado de directivas de publicador.  
  
3.  Agregue el ensamblado a la caché global de ensamblados.  
  
 Se describe el esquema de directiva de publicador en [Redirecting Assembly Versions](../../../docs/framework/configure-apps/redirect-assembly-versions.md). El ejemplo siguiente muestra un editor de archivo de directiva que redirige una versión de `myAssembly` a otro.  
  
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
  
 Para obtener información sobre cómo especificar un código base, vea [especificar la ubicación del ensamblado](../../../docs/framework/configure-apps/specify-assembly-location.md).  
  
## <a name="creating-the-publisher-policy-assembly"></a>Crear el ensamblado de directivas de publicador  
 Use la [Assembly Linker (Al.exe)](../../../docs/framework/tools/al-exe-assembly-linker.md) para crear el ensamblado de directivas de publicador.  
  
#### <a name="to-create-a-publisher-policy-assembly"></a>Para crear un ensamblado de directivas de publicador  
  
1.  En el símbolo del sistema, escriba el siguiente comando:  
  
     **al/Link:** *directivas* **/out:** *publisherPolicyAssemblyFile* **/keyfile:**  *keyPairFile* **/Platform:** *processorArchitecture*  
  
     En este comando:  
  
    -   El *directivas* argumento es el nombre del archivo de directiva de publicador.  
  
    -   El *publisherPolicyAssemblyFile* argumento es el nombre del ensamblado de directiva de publicador que da como resultado de este comando. El nombre de archivo de ensamblado debe tener el formato:  
  
         **Directiva.** *número principal* **.** *número secundario* **.** *nombre de ensamblado principal* **.dll**  
  
    -   El *keyPairFile* argumento es el nombre del archivo que contiene el par de claves. Debe firmar el ensamblado y el ensamblado de directivas del publicador con el mismo par de claves.  
  
    -   El *processorArchitecture* argumento identifica la plataforma de destino de un ensamblado específico del procesador.  
  
        > [!NOTE]
        >  La capacidad para tener como destino una arquitectura de procesador específico es nueva en la versión 2.0 de .NET Framework.  
  
     El siguiente comando crea un ensamblado de directivas de publicador denominado `policy.1.0.myAssembly` desde un archivo de directiva de publicador llama `pub.config`, asigna un nombre seguro al ensamblado mediante el par de claves en el `sgKey.snk` de archivos y especifica que el ensamblado tiene como destino el x86 arquitectura de procesador.  
  
    ```  
    al /link:pub.config /out:policy.1.0.myAssembly.dll /keyfile:sgKey.snk /platform:x86  
    ```  
  
     El ensamblado de directivas de publicador debe coincidir con la arquitectura del procesador del ensamblado que se aplica. Por lo tanto, si el ensamblado tiene un <xref:System.Reflection.AssemblyName.ProcessorArchitecture%2A> valor <xref:System.Reflection.ProcessorArchitecture.MSIL>, el ensamblado de directivas de publicador para dicho ensamblado debe crearse con `/platform:anycpu`. Debe proporcionar otro ensamblado de directivas de publicador para cada ensamblado específico del procesador.  
  
     Una consecuencia de esta regla es que con el fin de cambiar la arquitectura de procesador para un ensamblado, debe cambiar el componente principal o secundario del número de versión, por lo que puede proporcionar un nuevo ensamblado de directivas de publicador con la arquitectura correcta del procesador. El ensamblado de directiva de publicador anterior no puede reparar el ensamblado cuando el ensamblado tiene una arquitectura de procesador distinta.  
  
     Otra consecuencia es que la versión 2.0 del vinculador no puede utilizarse para crear un ensamblado de directivas de publicador para un ensamblado compilado con versiones anteriores de .NET Framework, porque siempre especifica la arquitectura del procesador.  
  
## <a name="adding-the-publisher-policy-assembly-to-the-global-assembly-cache"></a>Agregar el ensamblado de directivas de publicador a la caché Global de ensamblados  
 Use la [herramienta caché Global de ensamblados (Gacutil.exe)](../../../docs/framework/tools/gacutil-exe-gac-tool.md) para agregar el ensamblado de directivas de publicador a la caché global de ensamblados.  
  
#### <a name="to-add-the-publisher-policy-assembly-to-the-global-assembly-cache"></a>Para agregar el ensamblado de directivas de publicador a la caché global de ensamblados  
  
1.  En el símbolo del sistema, escriba el siguiente comando:  
  
     **gacutil /i***publisherPolicyAssemblyFile*   
  
     El comando siguiente agrega `policy.1.0.myAssembly.dll` a la caché global de ensamblados.  
  
    ```  
    gacutil /i policy.1.0.myAssembly.dll  
    ```  
  
    > [!IMPORTANT]
    >  No se puede agregar el ensamblado de directivas de publicador a la caché global de ensamblados, a menos que se encuentra el archivo de directiva de publicador original en el mismo directorio que el ensamblado.  
  
## <a name="see-also"></a>Vea también  
 [Programar con ensamblados](../../../docs/framework/app-domains/programming-with-assemblies.md)  
 [Cómo el motor en tiempo de ejecución ubica ensamblados](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)  
 [Configurar aplicaciones](../../../docs/framework/configure-apps/index.md)  
 [Configurar aplicaciones de .NET Framework](https://msdn.microsoft.com/library/d789b592-fcb5-4e3d-8ac9-e0299adaaa42)  
 [Esquema de la configuración de Common Language Runtime](../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [Esquema de los archivos de configuración](../../../docs/framework/configure-apps/file-schema/index.md)  
 [Redirigir versiones de ensamblado](../../../docs/framework/configure-apps/redirect-assembly-versions.md)
