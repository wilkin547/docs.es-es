---
title: "Nombres de ensamblado | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-bcl"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "ensamblados [.NET Framework], nombres"
  - "nombres [.NET Framework], ensamblados"
ms.assetid: 8f8c2c90-f15d-400e-87e7-a757e4f04d0e
caps.latest.revision: 14
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 14
---
# Nombres de ensamblado
El nombre de un ensamblado se almacena en los metadatos y tiene efectos importantes en el ámbito del ensamblado y en su uso en una aplicación.  Un ensamblado con nombre seguro especifica un nombre completo que incluye el nombre del ensamblado, la referencia cultural, la clave pública y el número de versión.  Normalmente se le conoce como el nombre para mostrar y, en el caso de ensamblados cargados, es posible su obtención utilizando la propiedad <xref:System.Reflection.Assembly.FullName%2A>.  
  
 El motor en tiempo de ejecución utiliza esta información para localizar el ensamblado y distinguirlo de otros ensamblados con el mismo nombre.  Por ejemplo, un ensamblado con nombre seguro denominado `myTypes` podría tener el siguiente nombre completo:  
  
```  
myTypes, Version=1.0.1234.0, Culture=en-US, PublicKeyToken=b77a5c561934e089c, ProcessorArchitecture=msil  
```  
  
> [!NOTE]
>  En la versión 2.0 de .NET Framework, se agrega a la identidad del ensamblado a la arquitectura del procesador para permitir versiones específicas de procesador de ensamblados.  Puede crear versiones de un ensamblado cuya identidad sólo se diferencia en la arquitectura del procesador, por ejemplo las versiones específicas del procesador de 32 bits y de 64 bits.  La arquitectura del procesador no es necesaria en los nombres seguros.  Para obtener más información, vea <xref:System.Reflection.AssemblyName.ProcessorArchitecture%2A?displayProperty=fullName>.  
  
 En este ejemplo, el nombre completo indica que el ensamblado `myTypes` tiene un nombre seguro con un símbolo \(token\) de clave pública, que la referencia cultural es inglés de EE.UU. y que el número de versión es 1.0.1234.0.  La arquitectura del procesador es "msil", lo que significa que se compilará just\-in\-time \(JIT\) a código de 32 bits o 64 bits en función del tipo de sistema operativo y de procesador.  
  
 El código que solicita tipos en un ensamblado debe utilizar un nombre de ensamblado completo.  Esto se denomina enlace completo.  Cuando se hace referencia a un ensamblado en .NET Framework, no se admite el enlace parcial, ya que sólo especifica un nombre de ensamblado.  
  
 Todas las referencias a los ensamblados que componen .NET Framework también deben incluir el nombre completo del ensamblado.  Por ejemplo, para hacer referencia al ensamblado System.Data de .NET Framework versión 1.0, habría que incluir lo siguiente:  
  
```  
  
System.data, version=1.0.3300.0, Culture=neutral, PublicKeyToken=b77a5c561934e089  
  
```  
  
 Observe que la versión corresponde al número de versión de todos los ensamblados incluidos con .NET Framework 1.0.  En los ensamblados de .NET Framework, el valor de la referencia cultural siempre es neutra y el de clave pública el mismo que aparece en el ejemplo anterior.  
  
 Por ejemplo, para agregar una referencia de ensamblado a un archivo de configuración para configurar un agente de escucha de seguimiento, deberá incluir el nombre completo del ensamblado del sistema .NET Framework:  
  
```  
<add name="myListener" type="System.Diagnostics.TextWriterTraceListener, System, Version=1.0.3300.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" initializeData="c:\myListener.log" />  
```  
  
> [!NOTE]
>  El motor en tiempo de ejecución no distingue mayúsculas y minúsculas en los nombres que se enlazan a un ensamblado, pero conserva lo que se use en el nombre de ensamblado.  Hay varias herramientas en el control de nombres del ensamblado de [!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)] que distinguen entre mayúsculas y minúsculas.  Para obtener mejores resultados, administre los nombres de ensamblado como si hubiera distinción entre mayúsculas y minúsculas.  
  
## Dar nombre a los componentes de aplicaciones  
 El motor en tiempo de ejecución no tiene en cuenta el nombre de archivo para determinar la identidad de un ensamblado.  La identidad del ensamblado, formada por el nombre, la versión, la referencia cultural y el nombre seguro del ensamblado, tiene que quedar clara para el motor en tiempo de ejecución.  
  
 Por ejemplo, si tiene un ensamblado denominado myAssembly.exe que hace referencia a un ensamblado denominado myAssembly.dll, el enlace se realizará correctamente si ejecuta myAssembly.exe.  Sin embargo, si otra aplicación ejecuta myAssembly.exe utilizando el método <xref:System.AppDomain.ExecuteAssembly%2A?displayProperty=fullName>, el motor en tiempo de ejecución determina que "myAssembly" ya está cargado cuando myAssembly.exe solicita el enlace a "myAssembly". En este caso, myAssembly.dll no se carga nunca.  Puesto que myAssembly.exe no contiene el tipo solicitado, se produce una excepción <xref:System.TypeLoadException>.  
  
 Para evitar este problema, asegúrese de que los ensamblados que forman la aplicación no tienen el mismo nombre completo de ensamblado o coloque los ensamblados con el mismo nombre en directorios distintos.  
  
> [!NOTE]
>  Si coloca un ensamblado en la caché global de ensamblados, el nombre de archivo del ensamblado debe coincidir con el nombre del ensamblado, aunque no es necesario que la extensión de nombre de archivo coincida \(como .exe o .dll\).  Por ejemplo, si el nombre de archivo de un ensamblado es myAssembly.dll, el nombre del ensamblado tiene que ser myAssembly.  Los ensamblados privados que sólo se implementan en el directorio de aplicación raíz pueden tener un nombre que no sea el mismo que el nombre de archivo.  
  
## Vea también  
 [Cómo: Determinar el nombre completo de un ensamblado](../../../docs/framework/app-domains/how-to-determine-assembly-fully-qualified-name.md)   
 [Crear ensamblados](../../../docs/framework/app-domains/create-assemblies.md)   
 [Ensamblados con nombre seguro](../../../docs/framework/app-domains/strong-named-assemblies.md)   
 [Caché global de ensamblados](../../../docs/framework/app-domains/gac.md)   
 [Cómo el motor en tiempo de ejecución ubica ensamblados](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)   
 [Programar con ensamblados](../../../docs/framework/app-domains/programming-with-assemblies.md)