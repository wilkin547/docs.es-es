---
title: "C&#243;mo: Crear una directiva de publicador | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "GAC (caché global de ensamblados), ensamblado de directivas del editor"
  - "caché global de ensamblados, ensamblado de directivas del editor"
  - "ensamblado de directivas del editor"
  - "archivos de directivas del editor"
ms.assetid: 8046bc5d-2fa9-4277-8a5e-6dcc96c281d9
caps.latest.revision: 15
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 15
---
# C&#243;mo: Crear una directiva de publicador
Los proveedores de ensamblados pueden indicar que las aplicaciones deben usar una versión más reciente de un ensamblado incluyendo un archivo de directivas del editor con el ensamblado actualizado.  El archivo de directivas del editor especifica la redirección del ensamblado y la configuración del código base, además de utilizar el mismo formato que un archivo de configuración de la aplicación.  El archivo de directivas del editor se compila en un ensamblado y se ubica en la caché global de ensamblados.  
  
 El procedimiento para crear una directiva del editor se compone de tres pasos:  
  
1.  Cree un archivo de directivas del editor.  
  
2.  Cree un ensamblado de directivas del editor.  
  
3.  Agregue dicho ensamblado a la caché global de ensamblados.  
  
 El esquema de la directiva del editor se describe en [Redirigir versiones de ensamblado](../../../docs/framework/configure-apps/redirect-assembly-versions.md).  En el siguiente ejemplo, se muestra un archivo de directivas del editor que redirige una versión de `myAssembly` a otra.  
  
```  
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
  
 Para saber cómo especificar un código base, vea [Especificar una ubicación de ensamblado](../../../docs/framework/configure-apps/specify-assembly-location.md).  
  
## Crear el ensamblado de directivas del publicador  
 Utilice la herramienta [Assembly Linker \(Al.exe\)](../../../docs/framework/tools/al-exe-assembly-linker.md) para crear el ensamblado de directivas del editor.  
  
#### Para crear un ensamblado de directivas del editor  
  
1.  Escriba el comando siguiente en el símbolo del sistema:  
  
     **al \/link:** *archivoDeDirectivasDelPublicador* **\/out:** *archivoDeEnsambladoDeDirectivasDelPublicador* **\/keyfile:** *archivoDeParDeClaves* **\/platform:** *arquitecturaDelProcesador*  
  
     En este comando:  
  
    -   El argumento *Archivo de directivas del editor* es el nombre del archivo de directivas del editor.  
  
    -   El argumento *Archivo del ensamblado de directivas del editor* es el nombre del ensamblado de directivas del editor que es el resultado de este comando.  El nombre de archivo del ensamblado debe tener el siguiente formato:  
  
         **policy.** *númeroPrincipal* **.** *númeroSecundario* **.** *nombreDelEnsambladoPrincipal* **.dll**  
  
    -   El argumento *Archivo de par de claves* es el nombre del archivo que contiene el par de claves.  Es necesario firmar el ensamblado y el ensamblado de directivas del editor con el mismo par de claves.  
  
    -   El argumento *Arquitectura de procesador* identifica la plataforma a la que va dirigido un ensamblado específico del procesador.  
  
        > [!NOTE]
        >  La capacidad de dirigirse a una arquitectura de procesador concreta es nueva en la versión 2.0 de .NET Framework.  
  
     El siguiente comando crea un ensamblado de directivas del editor denominado `policy.1.0.myAssembly` a partir de un archivo de directivas del editor denominado `pub.config`, asigna un nombre seguro al ensamblado mediante el par de claves del archivo `sgKey.snk` y especifica que el ensamblado va dirigido a la arquitectura de procesador x86.  
  
    ```  
    al /link:pub.config /out:policy.1.0.myAssembly.dll /keyfile:sgKey.snk /platform:x86  
    ```  
  
     El ensamblado de directivas del editor debe coincidir con la arquitectura del procesador del ensamblado al que se aplica.  Por tanto, si su ensamblado tiene un valor <xref:System.Reflection.AssemblyName.ProcessorArchitecture%2A> de <xref:System.Reflection.ProcessorArchitecture>, el ensamblado de directivas del editor para ese ensamblado se debe crear con `/platform:anycpu`.  Debe proporcionar un ensamblado de directivas del editor independiente para cada ensamblado específico del procesador.  
  
     Una consecuencia de esta regla es que, para cambiar la arquitectura del procesador para un ensamblado, debe cambiar el componente principal o secundario del número de versión, con el fin de proporcionar un nuevo ensamblado de directivas del editor con la arquitectura del procesador correcta.  El ensamblado de directivas del editor anterior no puede reparar el ensamblado cuando éste tiene una arquitectura del procesador diferente.  
  
     Otra consecuencia es que la versión 2.0 del vinculador no se puede utilizar para crear un ensamblado de directivas del editor para un ensamblado compilado mediante versiones anteriores de .NET Framework, porque siempre especifica la arquitectura del procesador.  
  
## Agregar el ensamblado de directivas del publicador a la caché global de ensamblados  
 Use la [herramienta Caché global de ensamblados \(Gacutil.exe\)](../../../docs/framework/tools/gacutil-exe-gac-tool.md) para agregar el ensamblado de directivas del editor a la caché global de ensamblados.  
  
#### Para agregar el ensamblado de directivas del editor a la caché global de ensamblados  
  
1.  Escriba el comando siguiente en el símbolo del sistema:  
  
     **gacutil \/i**  *nombreDelEnsambladoDeDirectivasDelPublicador*  
  
     El siguiente comando agrega `policy.1.0.myAssembly.dll` a la caché global de ensamblados.  
  
    ```  
    gacutil /i policy.1.0.myAssembly.dll  
    ```  
  
    > [!IMPORTANT]
    >  El ensamblado de directivas del editor no se puede agregar a la caché global de ensamblados a menos que el archivo de directiva del editor original se encuentre en el mismo directorio que el ensamblado.  
  
## Vea también  
 [Programar con ensamblados](../../../docs/framework/app-domains/programming-with-assemblies.md)   
 [Cómo el motor en tiempo de ejecución ubica ensamblados](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)   
 [Configurar aplicaciones](../../../docs/framework/configure-apps/index.md)   
 [Configuring .NET Framework Apps](http://msdn.microsoft.com/es-es/d789b592-fcb5-4e3d-8ac9-e0299adaaa42)   
 [Esquema de la configuración de Common Language Runtime](../../../docs/framework/configure-apps/file-schema/runtime/index.md)   
 [Esquema de los archivos de configuración](../../../docs/framework/configure-apps/file-schema/index.md)   
 [Redirigir versiones de ensamblado](../../../docs/framework/configure-apps/redirect-assembly-versions.md)