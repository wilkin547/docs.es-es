---
title: Ejecución en paralelo en .NET Framework
ms.date: 03/30/2017
helpviewer_keywords:
- side-by-side execution
ms.assetid: 649f1342-766b-49e6-a90d-5b019a751e11
ms.openlocfilehash: e965702943149d3ed34be39bb2923ad52dcf90ca
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "79181643"
---
# <a name="side-by-side-execution-in-the-net-framework"></a>Ejecución en paralelo en .NET Framework

La ejecución en paralelo es la capacidad de ejecutar múltiples versiones de una aplicación o componente en el mismo equipo. Se pueden tener varias versiones de Common Language Runtime y varias versiones de las aplicaciones y componentes que utilice una versión del motor en tiempo de ejecución, de forma simultánea y en el mismo equipo.  
  
La ilustración siguiente muestra varias aplicaciones que utilizan dos versiones diferentes del motor en tiempo de ejecución en el mismo equipo. Las aplicaciones A, B y C utilizan la versión 1.0 del motor en tiempo de ejecución, mientras que la aplicación D utiliza la versión 1.1.  
  
![Ejecución en paralelo de versiones diferentes del tiempo de ejecución](./media/side-by-side-execution/side-by-side-runtime-execution.gif)  
  
.NET Framework está formado por Common Language Runtime y una colección de ensamblados que contienen los tipos de la API. El motor en tiempo de ejecución y los ensamblados de .NET Framework tienen versiones independientes. Por ejemplo, la versión 4.0 del motor en tiempo de ejecución es en realidad la versión 4.0.319, mientras que la versión 1.0 de los ensamblados de .NET Framework es la versión 1.0.3300.0.  
  
La ilustración siguiente muestra varias aplicaciones que utilizan dos versiones diferentes de un componente en el mismo equipo. Las aplicaciones A y B utilizan la versión 1.0 del componente mientras que la aplicación C utiliza la versión 2.0 del mismo componente.  
  
![Diagrama en el que se muestra la ejecución en paralelo de un componente.](./media/side-by-side-execution/side-by-side-component-execution.gif)  
  
La ejecución en paralelo ofrece un mayor control sobre las versiones de un componente a las que se enlaza una aplicación, y sobre la versión del motor en tiempo de ejecución que utiliza una aplicación.  
  
## <a name="benefits-of-side-by-side-execution"></a>Ventajas de la ejecución en paralelo  

Antes de Windows XP y de .NET Framework, se producían conflictos en las DLL porque las aplicaciones no podían distinguir las versiones incompatibles del mismo código. La información de los tipos contenida en una DLL se enlazaba únicamente a un nombre de archivo. Una aplicación no podía saber de ninguna manera si los tipos incluidos en una DLL eran los mismos los tipos con los que se había compilado la aplicación. Como consecuencia de esto, una nueva versión de un componente podía sobrescribir la versión antigua e interrumpir las aplicaciones.  
  
La ejecución en paralelo y .NET Framework proporcionan las siguientes características que eliminan los conflictos con las DLL:  
  
- Ensamblados con nombre seguro  
  
     La ejecución en paralelo utiliza ensamblados con nombre seguro para enlazar la información de los tipos a una versión específica de un ensamblado. De este modo, se impide que una aplicación o componente se enlace a una versión no válida de un ensamblado. Los ensamblados con nombre seguro también permiten múltiples versiones de un archivo en el mismo equipo y que las aplicaciones las utilicen. Para más información, vea [Ensamblados con nombre seguro](../../standard/assembly/strong-named.md).  
  
- Almacenamiento de código con identificación de versión  
  
     .NET Framework ofrece un almacenamiento de código con identificación de la versión en la caché global de ensamblados. La caché global de ensamblados es una memoria caché de código que afecta a todo el equipo y que existe en los equipos con .NET Framework. Almacena ensamblados en función de la información de versión, referencia cultural y editor, y admite múltiples versiones de componentes y aplicaciones. Para obtener más información, vea [Global Assembly Cache](../app-domains/gac.md) (Caché global de ensamblados).  
  
- Aislamiento.  
  
     Con .NET Framework, puede crear aplicaciones y componentes que se ejecutan de forma aislada. El aislamiento es un componente esencial de la ejecución en paralelo. Implica que se reconocen los recursos que se usan y que se comparten con confianza entre varias versiones de una aplicación o un componente. El aislamiento también incluye el almacenamiento de archivos en el modo específico de la versión. Para obtener más información sobre el aislamiento, vea [Guidelines for Creating Components for Side-by-Side Execution](guidelines-for-creating-components-for-side-by-side-execution.md) (Instrucciones para crear componentes para la ejecución en paralelo).  
  
## <a name="version-compatibility"></a>Compatibilidad de versiones  

Las versiones 1.0 y 1.1 de .NET Framework se han diseñado para que sean compatibles entre sí. Una aplicación compilada con la versión 1.0 de .NET Framework debe poder ejecutarse en la versión 1.1 y, viceversa, una aplicación creada con la versión 1.1 de .NET Framework debe poder ejecutarse en la versión 1.0. No obstante, tenga en cuenta que las características de la API agregada a la versión 1.1 de .NET Framework no funcionarán con la versión 1.0 de .NET Framework. Las aplicaciones creadas con la versión 2.0 sólo se ejecutarán en dicha versión. Las aplicaciones creadas con la versión 2.0 no se ejecutarán en la versión 1.1 ni en las anteriores.  
  
Las versiones de .NET Framework se tratan como una sola unidad formada por el motor en tiempo de ejecución y los ensamblados asociados de .NET Framework (que se conoce como unificación de ensamblados). Se puede redirigir el enlace de ensamblados para incluir otras versiones de los ensamblados de .NET Framework, pero reemplazar el enlace de ensamblados predeterminado puede ser peligroso y se debe probar rigurosamente antes de su implementación.  
  
## <a name="locating-runtime-version-information"></a>Buscar información de versión del motor en tiempo de ejecución  

La información sobre la versión del motor en tiempo de ejecución utilizada en la compilación de una aplicación o componente y las versiones del motor en tiempo de ejecución que requiere una aplicación para ejecutarse se almacena en dos ubicaciones. Cuando se compila una aplicación o un componente, la información sobre la versión del motor en tiempo de ejecución utilizada para la compilación se almacena en el ejecutable administrado. La información de las versiones del motor en tiempo de ejecución que requiere una aplicación o componente se almacena en el archivo de configuración de la aplicación.  
  
### <a name="runtime-version-information-in-the-managed-executable"></a>Información de versión del motor en tiempo de ejecución en el ejecutable administrado  

El encabezado del archivo portable ejecutable (PE) de las aplicaciones y componentes administrados contiene información acerca de la versión del motor en tiempo de ejecución utilizada en su compilación. Common Language Runtime utiliza esta información para determinar la versión más adecuada del motor en tiempo de ejecución que se requiere para ejecutar la aplicación.  
  
### <a name="runtime-version-information-in-the-application-configuration-file"></a>Información de versión del motor en tiempo de ejecución en el archivo de configuración  

Además de la información en el encabezado del archivo PE, se puede implementar una aplicación con un archivo de configuración de la aplicación que proporciona la información de versión del motor en tiempo de ejecución. El archivo de configuración de la aplicación es un archivo basado en lenguaje XML creado por el desarrollador de aplicaciones y que se suministra con una aplicación. El [elemento \<requiredRuntime>](../configure-apps/file-schema/startup/requiredruntime-element.md) de la [sección \<startup>](../configure-apps/file-schema/startup/startup-element.md), si está presente en este archivo, especifica qué versiones del tiempo de ejecución y de un componente admite la aplicación. También se puede utilizar este archivo para probar la compatibilidad de una aplicación con distintas versiones del motor en tiempo de ejecución.  
  
El código no administrado, incluidas las aplicaciones COM y COM+, puede tener archivos de configuración de la aplicación que el motor en tiempo de ejecución utiliza para interactuar con código administrado. El archivo de configuración de la aplicación afecta a cualquier código administrado que se active mediante COM. Este archivo puede especificar las versiones del motor en tiempo de ejecución que son compatibles, así como las redirecciones de ensamblado. De forma predeterminada, las aplicaciones de interoperabilidad COM que llaman a código administrado utilizan la última versión del motor en tiempo de ejecución instalada en el equipo.  
  
 Para obtener más información sobre los archivos de configuración de la aplicación, vea [Configuring Apps](../configure-apps/index.md) (Configurar aplicaciones).  
  
## <a name="determining-which-version-of-the-runtime-to-load"></a>Determinar qué versión del motor en tiempo de ejecución debe cargarse  

Common Language Runtime usa la siguiente información para determinar qué versión del tiempo de ejecución se debe cargar para una aplicación:  
  
- Versiones del tiempo de ejecución que hay disponibles.  
  
- Versiones del tiempo de ejecución que admite una aplicación.  
  
### <a name="supported-runtime-versions"></a>Versiones del tiempo de ejecución admitidas  

Common Language Runtime usa el archivo de configuración de la aplicación y el encabezado del archivo portable ejecutable (PE) para determinar qué versión del tiempo de ejecución admite una aplicación. Si no hay ningún archivo de configuración de la aplicación, Common Language Runtime carga la versión del tiempo de ejecución especificada en el encabezado del archivo PE de la aplicación, si esa versión está disponible.  
  
Si hay un archivo de configuración de la aplicación, Common Language Runtime determina la versión que debe cargar en función de los resultados del proceso siguiente:  
  
1. El tiempo de ejecución examina el [elemento \<supportedRuntime>](../configure-apps/file-schema/startup/supportedruntime-element.md) en el archivo de configuración de la aplicación. Si hay una o varias de las versiones del tiempo de ejecución admitidas especificadas en el elemento **\<supportedRuntime>** , el tiempo de ejecución carga la versión del tiempo de ejecución especificada por el primer elemento **\<supportedRuntime>** . Si esta versión no está disponible, el tiempo de ejecución examina el siguiente elemento **\<supportedRuntime>** e intenta cargar la versión del tiempo de ejecución especificada. Si esta versión del tiempo de ejecución no está disponible, se examinan los siguientes elementos **\<supportedRuntime>** . Si ninguna de las versiones del tiempo de ejecución admitidas está disponible, Common Language Runtime no puede cargar una versión del tiempo de ejecución y muestra un mensaje al usuario (consulte el paso 3).  
  
2. Common Language Runtime lee el encabezado del archivo PE del archivo ejecutable de la aplicación. Si la versión del tiempo de ejecución especificada por el encabezado del archivo PE está disponible, Common Language Runtime carga esa versión. Si la versión del tiempo de ejecución especificada no está disponible, Common Language Runtime busca una versión del tiempo de ejecución que Microsoft determine que es compatible con la versión del tiempo de ejecución del encabezado PE. Si no se encuentra esa versión, el proceso continúa en el paso 3.  
  
3. Common Language Runtime muestra un mensaje que indica que la versión del tiempo de ejecución admitida por la aplicación no está disponible. El tiempo de ejecución no se carga.  
  
    > [!NOTE]
    > Para suprimir la presentación de este mensaje, use el valor NoGuiFromShim en la clave del Registro HKLM\Software\Microsoft\\.NETFramework o use la variable de entorno COMPLUS_NoGuiFromShim. Por ejemplo, puede suprimir el mensaje para las aplicaciones que normalmente no interactúan con el usuario, como las instalaciones desatendidas o los servicios de Windows. Cuando se suprime la presentación de este mensaje, el tiempo de ejecución escribe un mensaje en el registro de eventos.  Establezca el valor del Registro NoGuiFromShim en 1 para suprimir este mensaje para todas las aplicaciones en un equipo. También puede establecer la variable de entorno COMPLUS_NoGuiFromShim en 1 para suprimir el mensaje para las aplicaciones que se ejecutan en un contexto de usuario determinado.  
  
> [!NOTE]
> Después de que se cargue una versión del tiempo de ejecución, las redirecciones de enlace de ensamblados pueden especificar que se cargue una versión distinta de un ensamblado de .NET Framework individual. Estas redirecciones de enlace afectan solo al ensamblado específico que se redirige.  
  
## <a name="partially-qualified-assembly-names-and-side-by-side-execution"></a>Nombres de ensamblados parciales y ejecución en paralelo  

Dado que son un posible origen de problemas en paralelo, las referencias de ensamblados parciales solo pueden usarse para enlazar a ensamblados dentro de un directorio de aplicación. Evite las referencias de ensamblados parciales en el código.  
  
Para reducir las referencias de ensamblados parciales en el código, puede usar el elemento [\<qualifyAssembly>](../configure-apps/file-schema/runtime/qualifyassembly-element.md) en un archivo de configuración de la aplicación para completar las referencias de ensamblados parciales que se producen en el código. Use el elemento **\<qualifyAssembly>** para especificar solo los campos que no se han establecido en la referencia parcial. La identidad del ensamblado enumerada en el atributo **fullName** debe contener toda la información necesaria para completar el nombre del ensamblado: nombre del ensamblado, clave pública, referencia cultural y versión.  
  
 En el ejemplo siguiente se muestra la entrada del archivo de configuración de la aplicación para completar un ensamblado llamado `myAssembly`.  
  
```xml  
<assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">
<qualifyAssembly partialName="myAssembly"
fullName="myAssembly,  
      version=1.0.0.0,
publicKeyToken=...,
      culture=neutral"/>
</assemblyBinding>
```  
  
 Cada vez que una instrucción de carga de ensamblado hace referencia a `myAssembly`, estos valores del archivo de configuración hacen que el tiempo de ejecución convierta automáticamente la referencia parcial a `myAssembly` en una referencia completa. Por ejemplo, Assembly.Load("myAssembly") se convierte en Assembly.Load("myAssembly, version=1.0.0.0, publicKeyToken=..., culture=neutral").  
  
> [!NOTE]
> Puede usar el método **LoadWithPartialName** para omitir la restricción de Common Language Runtime que prohíbe cargar ensamblados con referencia parcial desde la caché global de ensamblados. Este método solo se debe usar en escenarios de acceso remoto que pueden producir problemas fácilmente en la ejecución en paralelo.  
  
## <a name="related-topics"></a>Temas relacionados  
  
|Título|Description|  
|-----------|-----------------|  
|[Cómo: Habilitar y deshabilitar redireccionamiento de enlaces automático](../configure-apps/how-to-enable-and-disable-automatic-binding-redirection.md)|Describe cómo enlazar una aplicación a una versión específica de un ensamblado.|  
|[Configurar el redireccionamiento del enlace de ensamblados](configuring-assembly-binding-redirection.md)|Explica cómo redirigir referencias a enlaces de ensamblados a una versión específica de los ensamblados de .NET Framework.|  
|[Ejecución en paralelo en proceso](in-process-side-by-side-execution.md)|Describe cómo se puede utilizar la activación del host en tiempo de ejecución en paralelo y en el mismo proceso para ejecutar varias versiones de CLR en un solo proceso.|  
|[Ensamblados de .NET](../../standard/assembly/index.md)|Proporciona una introducción general a los conceptos de los ensamblados.|  
|[Dominios de aplicación](../app-domains/application-domains.md)|Proporciona una introducción general a los conceptos de los dominios de aplicación.|  
  
## <a name="reference"></a>Referencia  

[\<supportedRuntime > Elemento](../configure-apps/file-schema/startup/supportedruntime-element.md)
