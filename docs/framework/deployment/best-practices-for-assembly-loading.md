---
title: "Procedimientos recomendados para cargar ensamblados | Microsoft Docs"
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
  - "ensamblados, enlace"
  - "ensamblados, cargar"
  - "errores de carga de ensamblados"
  - "contexto de carga predeterminado"
  - "contextos de carga"
  - "contexto de origen de carga"
  - "LoadFrom (método)"
  - "LoadWithPartialName (método)"
  - "TypeLoadException (clase), causas"
ms.assetid: 68d1c539-6a47-4614-ab59-4b071c9d4b4c
caps.latest.revision: 10
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 10
---
# Procedimientos recomendados para cargar ensamblados
En este artículo se abordan formas de evitar problemas de identidad de tipos que pueden causar errores como <xref:System.InvalidCastException>, <xref:System.MissingMethodException>, entre otros.  En el artículo se exponen las siguientes recomendaciones:  
  
-   [Comprender las ventajas y las desventajas de los contextos de carga](#load_contexts)  
  
-   [Evitar enlaces en nombres de ensamblado parciales](#avoid_partial_names)  
  
-   [Evitar la carga de un ensamblado en varios contextos](#avoid_loading_into_multiple_contexts)  
  
-   [Evitar la carga de varias versiones de un ensamblado en el mismo contexto](#avoid_loading_multiple_versions)  
  
-   [Considerar cambiar al contexto de carga predeterminado](#switch_to_default)  
  
 La primera recomendación, [comprender las ventajas y las desventajas de los contextos de carga](#load_contexts), proporciona información adicional para las demás recomendaciones, porque todas dependen del conocimiento de los contextos de carga.  
  
<a name="load_contexts"></a>   
## Comprender las ventajas y las desventajas de los contextos de carga  
 En un dominio de aplicación, los ensamblados se pueden cargar en uno de estos tres contextos, o se pueden cargar sin contexto:  
  
-   El contexto de carga predeterminado contiene ensamblados que se han encontrado sondeando la memoria caché global de ensamblados, el almacén de ensamblado de host si hospeda el runtime \(por ejemplo, SQL Server\) o las propiedades <xref:System.AppDomainSetup.ApplicationBase%2A> y <xref:System.AppDomainSetup.PrivateBinPath%2A> del dominio de aplicación.  La mayoría de las sobrecargas del método <xref:System.Reflection.Assembly.Load%2A> cargan los ensamblados en este contexto.  
  
-   El contexto de origen de carga contiene ensamblados que se cargan desde ubicaciones en las que no busca el cargador.  Por ejemplo, los complementos se podrían instalar en un directorio que no está bajo la ruta de la aplicación.  <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=fullName>, <xref:System.AppDomain.CreateInstanceFrom%2A?displayProperty=fullName> y <xref:System.AppDomain.ExecuteAssembly%2A?displayProperty=fullName> son ejemplos de métodos que realizan la carga mediante una ruta de acceso.  
  
-   El contexto de solo reflexión contiene ensamblados cargados con los métodos <xref:System.Reflection.Assembly.ReflectionOnlyLoadFrom%2A> y <xref:System.Reflection.Assembly.ReflectionOnlyLoad%2A>.  El código en este contexto no se puede ejecutar, por lo que no se trata aquí.  Para obtener más información, vea [How to: Load Assemblies into the Reflection\-Only Context](../../../docs/framework/reflection-and-codedom/how-to-load-assemblies-into-the-reflection-only-context.md).  
  
-   Si generó un ensamblado dinámico transitorio mediante emisión de la reflexión, el ensamblado no está en cualquier contexto.  Además, la mayoría de los ensamblados que se cargan con el método <xref:System.Reflection.Assembly.LoadFile%2A> se cargan sin contexto, y los ensamblados que se cargan desde las matrices de bytes se cargan sin contexto a menos que su identidad \(una vez aplicada la directiva\) establezca que están en la memoria caché global de ensamblados.  
  
 Los contextos de ejecución tienen ventajas y desventajas, que se comentan en las siguientes secciones.  
  
### Contexto de carga predeterminado  
 Cuando los ensamblados se cargan en el contexto de carga predeterminado, automáticamente se cargan sus dependencias.  Las dependencias que se cargan en el contexto de carga predeterminado se encuentran automáticamente para los ensamblados en el contexto de carga predeterminado o en el contexto de origen de carga.  La carga por identidad del ensamblado aumenta la estabilidad de las aplicaciones al asegurarse de que no se utilizan versiones desconocidas de ensamblados \(vea la sección [Evitar enlaces en nombres de ensamblado parciales](#avoid_partial_names)\).  
  
 Utilizar el contexto de carga predeterminado tiene las siguientes desventajas:  
  
-   Las dependencias que se cargan en otros contextos no están disponibles.  
  
-   No puede cargar ensamblados de ubicaciones externas a la ruta de sondeo en el contexto de carga predeterminado.  
  
### Contexto de origen de carga  
 El contexto de origen de carga permite cargar un ensamblado de una ruta de acceso que no se encuentra bajo la ruta de la aplicación y, por consiguiente, no está incluida en el sondeo.  Permite encontrar las dependencias y cargarlas desde esa ruta de acceso, porque el contexto mantiene la información de la ruta de acceso.  Además, los ensamblados en este contexto pueden utilizar dependencias que se cargan en el contexto de carga predeterminado.  
  
 La carga de ensamblados con el método <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=fullName> o con uno de los otros métodos de carga por ruta de acceso presenta las siguientes desventajas:  
  
-   Si ya se ha cargado un ensamblado con la misma identidad, <xref:System.Reflection.Assembly.LoadFrom%2A> devuelve el ensamblado cargado incluso si se ha especificado una ruta de acceso diferente.  
  
-   Si se carga un ensamblado con <xref:System.Reflection.Assembly.LoadFrom%2A> y después un ensamblado del contexto de carga predeterminado intenta cargar el mismo ensamblado por el nombre para mostrar, se producirá un error al cargar.  Esto puede ocurrir al deserializar un ensamblado.  
  
-   Si se carga un ensamblado con <xref:System.Reflection.Assembly.LoadFrom%2A>, y la ruta de acceso de sondeo incluye un ensamblado con la misma identidad pero en una ubicación diferente, se puede producir una excepción <xref:System.InvalidCastException>, <xref:System.MissingMethodException> o cualquier otro comportamiento inesperado.  
  
-   <xref:System.Reflection.Assembly.LoadFrom%2A> solicita <xref:System.Security.Permissions.FileIOPermissionAccess?displayProperty=fullName> y <xref:System.Security.Permissions.FileIOPermissionAccess?displayProperty=fullName>, o <xref:System.Net.WebPermission>, en la ruta de acceso especificada.  
  
-   Si existe una imagen nativa para el ensamblado, no se utiliza.  
  
-   El ensamblado no se puede cargar como código neutral de dominio.  
  
-   En .NET Framework, versiones 1.0 y 1.1, no se aplica ninguna directiva.  
  
### Sin contexto  
 Cargar sin contexto es la única opción para los ensamblados transitorios que se generan con emisión de reflexión.  Cargar sin contexto es la única manera de cargar múltiples ensamblados que tienen la misma identidad en un dominio de aplicación.  Se evita el trabajo de sondear.  
  
 Los ensamblados que se cargan desde matrices de bytes se cargan sin contexto a menos que la identidad del ensamblado, que se establece cuando se aplica la directiva, coincida con la identidad de un ensamblado de la memoria caché global de ensamblados; en ese caso, el ensamblado se carga desde la memoria caché global de ensamblados.  
  
 Cargar los ensamblados sin contexto presenta las siguientes desventajas:  
  
-   Otros ensamblados no pueden enlazar con los ensamblados que se cargan sin contexto, a menos que se controle el evento <xref:System.AppDomain.AssemblyResolve?displayProperty=fullName>.  
  
-   Las dependencias no se cargan automáticamente.  Puede cargarlas previamente sin contexto, cargarlas previamente en el contexto de carga predeterminado o cargarlas controlando el evento <xref:System.AppDomain.AssemblyResolve?displayProperty=fullName>.  
  
-   La carga de varios ensamblados con la misma identidad sin contexto puede producir problemas de identidad similares a los que produce la carga de ensamblados con la misma identidad en varios contextos.  Vea [Evitar la carga de un ensamblado en varios contextos](#avoid_loading_into_multiple_contexts).  
  
-   Si existe una imagen nativa para el ensamblado, no se utiliza.  
  
-   El ensamblado no se puede cargar como código neutral de dominio.  
  
-   En .NET Framework, versiones 1.0 y 1.1, no se aplica ninguna directiva.  
  
<a name="avoid_partial_names"></a>   
## Evitar enlaces en nombres de ensamblado parciales  
 El enlace de nombre parcial tiene lugar cuando se especifica solo parte del nombre para mostrar del ensamblado \(<xref:System.Reflection.Assembly.FullName%2A>\) al cargarlo.  Por ejemplo, podría llamar al método <xref:System.Reflection.Assembly.Load%2A?displayProperty=fullName> con el nombre sencillo del ensamblado, omitiendo la versión, la referencia cultural y el token de clave pública.  O podría llamar al método <xref:System.Reflection.Assembly.LoadWithPartialName%2A?displayProperty=fullName>, que primero llama al método <xref:System.Reflection.Assembly.Load%2A?displayProperty=fullName> y, si no logra encontrar el ensamblado, busca en la memoria caché global de ensamblados y carga la última versión disponible del ensamblado.  
  
 El enlace de nombre parcial puede producir muchos problemas, a saber:  
  
-   El método <xref:System.Reflection.Assembly.LoadWithPartialName%2A?displayProperty=fullName> podría cargar un ensamblado diferente con el mismo nombre sencillo.  Por ejemplo, dos aplicaciones podrían instalar dos ensamblados completamente diferentes con el nombre sencillo `GraphicsLibrary` en la memoria caché global de ensamblados.  
  
-   El ensamblado que se carga tal vez no sea compatible con versiones anteriores.  Por ejemplo, si no se especifica la versión puede suceder que se cargue una versión muy posterior a la versión para la que se escribió el programa.  Los cambios en la versión posterior podrían producir errores en su aplicación.  
  
-   El ensamblado que se carga podría no ser compatible con versiones posteriores.  Por ejemplo, tal vez haya compilado y probado la aplicación con la última versión de un ensamblado, pero el enlace parcial puede cargar una versión muy anterior que no tiene las características que usa su aplicación.  
  
-   La instalación de nuevas aplicaciones puede interrumpir las existentes.  Una aplicación que usa el método <xref:System.Reflection.Assembly.LoadWithPartialName%2A> se puede interrumpir si se instala una versión más reciente, incompatible, de un ensamblado compartido.  
  
-   Se puede producir una carga de dependencias inesperada.  Si carga dos ensamblados que comparten una dependencia, cargarlos con enlace parcial podría hacer que un ensamblado usara un componente que no se compiló ni se probó.  
  
 Debido a los problemas que puede causar, el método <xref:System.Reflection.Assembly.LoadWithPartialName%2A> está en desuso.  Recomendamos que utilice el método <xref:System.Reflection.Assembly.Load%2A?displayProperty=fullName> en su lugar y que especifique los nombres para mostrar completos de los ensamblados.  Vea [Comprender las ventajas y desventajas de los contextos de carga](#load_contexts) y [Considerar cambiar al contexto de carga predeterminado](#switch_to_default).  
  
 Si desea utilizar el método <xref:System.Reflection.Assembly.LoadWithPartialName%2A> porque facilita la carga de los ensamblados, tenga en cuenta que tener un error en la aplicación con un mensaje que identifica el ensamblado que falta probablemente proporcione mejor experiencia de usuario que usar una versión desconocida del ensamblado, algo que puede dar lugar a un comportamiento imprevisible y vulnerabilidades de seguridad.  
  
<a name="avoid_loading_into_multiple_contexts"></a>   
## Evitar la carga de un ensamblado en varios contextos  
 Cargar un ensamblado en varios contextos puede producir problemas de identidad de tipos.  Cargar el mismo tipo del mismo ensamblado en dos contextos diferentes es como cargar dos tipos diferentes con el mismo nombre.  Se produce una <xref:System.InvalidCastException> si intenta convertir un tipo en el otro, con un mensaje confuso que indica que el tipo `MyType` no se puede convertir en el tipo `MyType`.  
  
 Por ejemplo, suponga que la interfaz `ICommunicate` se declara en un ensamblado denominado `Utility`, al que se hace referencia en su programa y también en otros ensamblados que su programa carga.  Estos otros ensamblados contienen tipos que implementan la interfaz `ICommunicate` y permite que su programa los utilice.  
  
 Ahora considere lo que pasa cuando se ejecuta el programa.  Los ensamblados a los que se hace referencia en su programa se cargan en el contexto de carga predeterminado.  Si carga un ensamblado de destino por su identidad, utilizando el método <xref:System.Reflection.Assembly.Load%2A>, estará en el contexto de carga predeterminado, igual que sus dependencias.  Su programa y el ensamblado de destino utilizarán el mismo ensamblado `Utility`.  
  
 Sin embargo, suponga que carga el ensamblado de destino por la ruta de acceso del archivo, mediante el método <xref:System.Reflection.Assembly.LoadFile%2A>.  El ensamblado se carga sin ningún contexto, de manera que sus dependencias no se cargan automáticamente.  Podría tener un controlador para que el evento <xref:System.AppDomain.AssemblyResolve?displayProperty=fullName> proporcione la dependencia y podría cargar el ensamblado `Utility` sin contexto utilizando el método <xref:System.Reflection.Assembly.LoadFile%2A>.  Pero al crear una instancia de un tipo que está contenido en el ensamblado de destino e intenta asignarlo a una variable de tipo `ICommunicate`, se produce una <xref:System.InvalidCastException> porque el motor en tiempo de ejecución considera que las interfaces `ICommunicate` de las dos copias del ensamblado `Utility` son de tipos diferentes.  
  
 Hay muchos otros escenarios en los que un ensamblado se puede cargar en varios contextos.  El enfoque mejor es evitar los conflictos reubicando el ensamblado de destino en la ruta de la aplicación y utilizando el método <xref:System.Reflection.Assembly.Load%2A> con el nombre para mostrar completo.  A continuación, el ensamblado se carga en el contexto de carga predeterminado y ambos ensamblados utilizan el mismo ensamblado `Utility`.  
  
 Si el ensamblado de destino debe permanecer fuera de la ruta de la aplicación, use el método <xref:System.Reflection.Assembly.LoadFrom%2A> para cargarlo en el contexto de origen de la carga.  Si el ensamblado de destino se compiló con una referencia al ensamblado `Utility` de la aplicación, utilizará el ensamblado `Utility` que la aplicación ha cargado en el contexto de carga predeterminado.  Observe que se pueden producir problemas si el ensamblado de destino tiene una dependencia en una copia del ensamblado `Utility` ubicada fuera de la ruta de la aplicación.  Si ese ensamblado se carga en el contexto de origen de carga de antes de que la aplicación cargue el ensamblado `Utility`, se producirá un error al cargar la aplicación.  
  
 En la sección [Considerar cambiar al contexto de carga predeterminado](#switch_to_default) se describen las alternativas al uso de las cargas de la ruta de acceso del archivo como <xref:System.Reflection.Assembly.LoadFile%2A> y <xref:System.Reflection.Assembly.LoadFrom%2A>.  
  
<a name="avoid_loading_multiple_versions"></a>   
## Evitar la carga de varias versiones de un ensamblado en el mismo contexto  
 Cargar varias versiones de un ensamblado en un contexto de carga puede producir problemas de identidad de tipos.  Cargar el mismo tipo de dos versiones del mismo ensamblado es como cargar dos tipos diferentes con el mismo nombre.  Se produce una <xref:System.InvalidCastException> si intenta convertir un tipo en el otro, con un mensaje confuso que indica que el tipo `MyType` no se puede convertir en el tipo `MyType`.  
  
 Por ejemplo, su programa podría cargar una versión del ensamblado `Utility` directamente y después cargar otro ensamblado que carga una versión diferente del ensamblado `Utility`.  O un error de codificación puede hacer dos rutas de acceso del código diferentes de su aplicación carguen versiones diferentes de un ensamblado.  
  
 En el contexto de carga predeterminado, este problema se puede dar cuando se usa el método <xref:System.Reflection.Assembly.Load%2A?displayProperty=fullName> y se especifican nombres para mostrar completos de los ensamblados que incluyen números de versión diferentes.  Para los ensamblados que se cargan sin contexto, el problema se puede producir cuando se usa método <xref:System.Reflection.Assembly.LoadFile%2A?displayProperty=fullName> para cargar el mismo ensamblado de rutas de acceso diferentes.  El motor en tiempo de ejecución considera que dos ensamblados que se cargan desde rutas de acceso diferentes son diferentes, aunque su identidad sea la misma.  
  
 Además de los problemas de identidad de tipos, varias versiones de un ensamblado pueden producir un <xref:System.MissingMethodException> si un tipo que se carga desde una versión del ensamblado se pasa a código que espera ese tipo pero de otra versión.  Por ejemplo, el código espera un método que se agregó a la versión posterior.  
  
 Los errores más sutiles se pueden producir si el comportamiento del tipo se cambió entre las versiones.  Por ejemplo, un método podría producir una excepción inesperada o devolver un valor inesperado.  
  
 Revise atentamente el código para asegurarse de que se carga una versión del ensamblado únicamente.  Puede utilizar el método <xref:System.AppDomain.GetAssemblies%2A?displayProperty=fullName> para determinar qué ensamblados se cargan en una momento determinado.  
  
<a name="switch_to_default"></a>   
## Considerar cambiar al contexto de carga predeterminado  
 Examine el modelo de carga e implementación del ensamblado de la aplicación.  ¿Puede eliminar los ensamblados que se cargan desde matrices de bytes?  ¿Puede mover los ensamblados a la ruta de acceso de sondeo?  Si los ensamblados se encuentran en la memoria caché global de ensamblados o en la ruta de acceso de sondeo del dominio de la aplicación \(es decir, su <xref:System.AppDomainSetup.ApplicationBase%2A> y <xref:System.AppDomainSetup.PrivateBinPath%2A>\), puede cargar el ensamblado por su identidad.  
  
 Si no es posible colocar todos los ensamblados en la ruta de acceso de sondeo, considere alternativas como usar el modelo de complemento de .NET Framework, colocar los ensamblados en la memoria caché global de ensamblados o crear dominios de aplicación.  
  
### Considerar el uso del modelo de complemento de .NET Framework  
 Si está utilizando el contexto de origen de carga para implementar complementos, que normalmente no se instalan en la base de la aplicación, utilice el modelo de complemento de .NET Framework.  Este modelo proporciona el aislamiento en el nivel del dominio de aplicación o del proceso, por lo que no tiene necesidad de administrar los dominios de aplicación.  Para obtener información acerca del modelo de complemento, vea [Complementos y extensibilidad](../../../ml/index.xml).  
  
### Considerar el uso de la memoria caché global de ensamblados  
 Coloque los ensamblados en la memoria caché global de ensamblados para aprovechar la ventaja de una ruta de acceso de ensamblado compartida que está fuera de la base de la aplicación, sin perder las ventajas del contexto de carga predeterminado o sin asumir las desventajas de los demás contextos.  
  
### Considerar el uso de dominios de aplicación  
 Si determina que algunos de sus ensamblados no se pueden implementar en la ruta de acceso de sondeo de la aplicación, considere crear un nuevo dominio de aplicación para esos ensamblados.  Utilice <xref:System.AppDomainSetup> para crear el nuevo dominio de aplicación y la propiedad <xref:System.AppDomainSetup.ApplicationBase%2A?displayProperty=fullName> para especificar la ruta de acceso que contiene los ensamblados que desea cargar.  Si tiene varios directorios para sondear, puede establecer <xref:System.AppDomainSetup.ApplicationBase%2A> en un directorio raíz y utilizar la propiedad <xref:System.AppDomainSetup.PrivateBinPath%2A?displayProperty=fullName> para identificar los subdirectorios en los que se sondeará.  Alternativamente, puede crear varios dominios de aplicación y establecer <xref:System.AppDomainSetup.ApplicationBase%2A> de cada dominio de aplicación en la ruta de acceso adecuada para los ensamblados.  
  
 Observe que puede utilizar el método <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=fullName> para cargar estos ensamblados.  Dado que ahora están en la ruta de acceso de sondeo, se cargarán en el contexto de carga predeterminado en lugar de en el contexto de origen de carga.  Sin embargo, recomendamos cambiar al método <xref:System.Reflection.Assembly.Load%2A?displayProperty=fullName> y proporcionar nombres para mostrar completos del ensamblado para asegurarse de que siempre se utilizan las versiones correctas.  
  
## Vea también  
 <xref:System.Reflection.Assembly.Load%2A?displayProperty=fullName>   
 <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=fullName>   
 <xref:System.Reflection.Assembly.LoadFile%2A?displayProperty=fullName>   
 <xref:System.AppDomain.AssemblyResolve?displayProperty=fullName>   
 [Complementos y extensibilidad](../../../ml/index.xml)