---
title: Procedimientos recomendados para cargar ensamblados
ms.date: 03/30/2017
helpviewer_keywords:
- assemblies,binding
- LoadFrom method
- default load context
- TypeLoadException class,causes
- assembly loading errors
- load contexts
- assemblies,loading
- LoadWithPartialName method
- load-from context
ms.assetid: 68d1c539-6a47-4614-ab59-4b071c9d4b4c
ms.openlocfilehash: d1b6c2cd9f96a4acf48cbced48a86bc3e3409562
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75716588"
---
# <a name="best-practices-for-assembly-loading"></a>Procedimientos recomendados para cargar ensamblados
En este artículo se abordan formas de evitar problemas de identidad de tipos que pueden causar errores como <xref:System.InvalidCastException> o <xref:System.MissingMethodException>, entre otros. En él se ofrecen las siguientes recomendaciones:  
  
- [Comprenda las ventajas y las desventajas de los contextos de carga](#load_contexts)  
  
- [Evite los enlaces en nombres de ensamblado parciales](#avoid_partial_names)  
  
- [Evite la carga de un ensamblado en varios contextos](#avoid_loading_into_multiple_contexts)  
  
- [Evite la carga de varias versiones de un ensamblado en el mismo contexto](#avoid_loading_multiple_versions)  
  
- [Considere la posibilidad de cambiar al contexto de carga predeterminado](#switch_to_default)  
  
 La primera recomendación, [comprenda las ventajas y las desventajas de los contextos de carga](#load_contexts), proporciona información general para las demás recomendaciones, ya que todas dependen del conocimiento de los contextos de carga.  
  
<a name="load_contexts"></a>   
## <a name="understand-the-advantages-and-disadvantages-of-load-contexts"></a>Comprenda las ventajas y las desventajas de los contextos de carga  
 En un dominio de aplicación, los ensamblados se pueden cargar en uno de entre tres contextos o sin contexto:  
  
- El contexto de carga predeterminado contiene ensamblados que se encuentran al sondear la caché global de ensamblados, el almacén de ensamblado de host si el runtime está hospedado (por ejemplo, en SQL Server) y el <xref:System.AppDomainSetup.ApplicationBase%2A> y <xref:System.AppDomainSetup.PrivateBinPath%2A> del dominio de aplicación. La mayoría de las sobrecargas del método <xref:System.Reflection.Assembly.Load%2A> carga ensamblados en este contexto.  
  
- El contexto de origen de carga contiene ensamblados que se cargan desde ubicaciones en las que no busca el cargador. Por ejemplo, los complementos podrían instalarse en un directorio que no esté bajo la ruta de acceso de la aplicación. <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType>, <xref:System.AppDomain.CreateInstanceFrom%2A?displayProperty=nameWithType> y <xref:System.AppDomain.ExecuteAssembly%2A?displayProperty=nameWithType> son ejemplos de métodos que cargan por ruta de acceso.  
  
- El contexto de solo reflexión contiene ensamblados cargados con los métodos <xref:System.Reflection.Assembly.ReflectionOnlyLoad%2A> y <xref:System.Reflection.Assembly.ReflectionOnlyLoadFrom%2A>. No se puede ejecutar código en este contexto, por lo que no se trata aquí. Para obtener más información, vea [Cómo: Cargar ensamblados en el contexto de solo reflexión](../reflection-and-codedom/how-to-load-assemblies-into-the-reflection-only-context.md).  
  
- Si ha generado un ensamblado dinámico transitorio mediante la reflexión de la emisión, el ensamblado no está en ningún contexto. Además, la mayoría de los ensamblados que se carga mediante el método <xref:System.Reflection.Assembly.LoadFile%2A> lo hace sin contexto, mientras que los ensamblados que se cargan desde matrices de bytes lo hacen sin contexto a menos que su identidad (una vez aplicada la directiva) establezca que están en la caché global de ensamblados.  
  
 Los contextos de ejecución tienen ventajas y desventajas, como se explica en las secciones siguientes.  
  
### <a name="default-load-context"></a>Contexto de carga predeterminado  
 Cuando los ensamblados se cargan en el contexto de carga predeterminado, sus dependencias se cargan automáticamente. Las dependencias que se cargan en el contexto de carga predeterminado se encuentran automáticamente para los ensamblados en el contexto de carga predeterminado o en el contexto de origen de carga. La carga por identidad del ensamblado aumenta la estabilidad de las aplicaciones al garantizar que no se usen versiones desconocidas de ensamblados (vea la sección [Evite los enlaces en nombres de ensamblado parciales](#avoid_partial_names)).  
  
 El empleo del contexto de carga predeterminado tiene las siguientes desventajas:  
  
- Las dependencias que se cargan en otros contextos no están disponibles.  
  
- No es posible cargar ensamblados desde ubicaciones situadas fuera de la ruta de acceso de sondeo en el contexto de carga predeterminado.  
  
### <a name="load-from-context"></a>Contexto de origen de carga  
 El contexto de origen de carga permite cargar un ensamblado desde una ruta de acceso que no está en la ruta de acceso de la aplicación y que, por tanto, no está incluida en el sondeo. Permite encontrar y cargar dependencias desde esa ruta de acceso porque el contexto mantiene la información de la ruta de acceso. Además, los ensamblados de este contexto pueden usar dependencias que se cargan en el contexto de carga predeterminado.  
  
 La carga de ensamblados mediante el método <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType>, o alguno de los demás métodos que cargan por ruta de acceso, tiene las siguientes desventajas:  
  
- Si hay un ensamblado con la misma identidad ya cargado, <xref:System.Reflection.Assembly.LoadFrom%2A> devuelve el ensamblado cargado aunque se haya especificado otra ruta de acceso.  
  
- Si se carga un ensamblado con <xref:System.Reflection.Assembly.LoadFrom%2A> y después un ensamblado del contexto de carga predeterminado intenta cargar el mismo ensamblado por nombre para mostrar, se produce un error en el intento de carga. Esto puede ocurrir cuando se deserializa un ensamblado.  
  
- Si un ensamblado se carga con <xref:System.Reflection.Assembly.LoadFrom%2A> y la ruta de acceso de sondeo incluye un ensamblado con la misma identidad pero en otra ubicación, puede producirse una <xref:System.InvalidCastException>, <xref:System.MissingMethodException> u otro comportamiento inesperado.  
  
- <xref:System.Reflection.Assembly.LoadFrom%2A> exige <xref:System.Security.Permissions.FileIOPermissionAccess.Read?displayProperty=nameWithType> y <xref:System.Security.Permissions.FileIOPermissionAccess.PathDiscovery?displayProperty=nameWithType>, o <xref:System.Net.WebPermission>, en la ruta de acceso especificada.  
  
- Si existe una imagen nativa del ensamblado, no se usa.  
  
- No se puede cargar el ensamblado con dominio neutro.  
  
- En las versiones 1.0 y 1.1 de .NET Framework no se aplica la directiva.  
  
### <a name="no-context"></a>Sin contexto  
 La carga sin contexto es la única opción para los ensamblados transitorios generados con la emisión de la reflexión. La carga sin contexto es la única manera de cargar varios ensamblados con la misma identidad en un dominio de aplicación. Se evita el costo del sondeo.  
  
 Los ensamblados que se cargan desde matrices de bytes lo hacen sin contexto a menos que la identidad del ensamblado, que se establece al aplicar la directiva, coincide con la identidad de un ensamblado de la caché global de ensamblados; en ese caso, el ensamblado se carga desde la caché global de ensamblados.  
  
 La carga de ensamblados sin contexto presenta las siguientes desventajas:  
  
- No es posible enlazar otros ensamblados a ensamblados cargados sin contexto, a menos que controle el evento <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType>.  
  
- Las dependencias no se cargan automáticamente. Puede cargarlas previamente sin contexto, cargarlas previamente en el contexto de carga predeterminado o cargarlas mediante el control del evento <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType>.  
  
- La carga de varios ensamblados con la misma identidad sin contexto puede provocar problemas de identidad de tipos similares a los que produce la carga de ensamblados con la misma identidad en varios contextos. Vea [Evite la carga de un ensamblado en varios contextos](#avoid_loading_into_multiple_contexts).  
  
- Si existe una imagen nativa del ensamblado, no se usa.  
  
- No se puede cargar el ensamblado con dominio neutro.  
  
- En las versiones 1.0 y 1.1 de .NET Framework no se aplica la directiva.  
  
<a name="avoid_partial_names"></a>   
## <a name="avoid-binding-on-partial-assembly-names"></a>Evite los enlaces en nombres de ensamblado parciales  
 Los enlaces de nombre parcial se producen cuando se especifica solo parte del nombre para mostrar del ensamblado (<xref:System.Reflection.Assembly.FullName%2A>) al cargar un ensamblado. Por ejemplo, puede llamar al método <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> con solo el nombre simple del ensamblado, omitiendo la versión, la referencia cultural y el token de clave pública. O bien puede llamar al método <xref:System.Reflection.Assembly.LoadWithPartialName%2A?displayProperty=nameWithType>, que primero llama al método <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> y, si así no logra encontrar el ensamblado, busca en la caché global de ensamblados y carga la última versión disponible del ensamblado.  
  
 Los enlaces de nombre parcial pueden producir muchos problemas, incluidos los siguientes:  
  
- El método <xref:System.Reflection.Assembly.LoadWithPartialName%2A?displayProperty=nameWithType> puede cargar otro ensamblado con el mismo nombre simple. Por ejemplo, dos aplicaciones podrían instalar dos ensamblados completamente diferentes con el nombre simple `GraphicsLibrary` en la caché global de ensamblados.  
  
- El ensamblado cargado realmente podría no ser compatible con versiones anteriores. Por ejemplo, si no se especifica la versión, se podría cargar una versión muy posterior a aquella en que se escribiera originalmente el programa. Los cambios en la versión más reciente podrían provocar errores en la aplicación.  
  
- El ensamblado cargado realmente podría no ser compatible con versiones posteriores. Por ejemplo, podría haber compilado y probado la aplicación con la versión más reciente de un ensamblado, pero el enlace parcial podría cargar una versión muy anterior que no tuviera características que usa la aplicación.  
  
- Al instalar nuevas aplicaciones se podrían interrumpir aplicaciones existentes. Una aplicación que usa el método <xref:System.Reflection.Assembly.LoadWithPartialName%2A> puede interrumpirse al instalar una versión no compatible más reciente de un ensamblado compartido.  
  
- Se puede producir una carga de dependencias inesperada. Si carga dos ensamblados que comparten una dependencia, el cargarlos con enlace parcial podría dar lugar a que uno usara un componente con el que no se hubiera compilado ni probado.  
  
 Debido a los problemas que puede ocasionar, el método <xref:System.Reflection.Assembly.LoadWithPartialName%2A> se ha marcado como obsoleto. Se recomienda usar el método <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> en su lugar y especificar nombres para mostrar de ensamblado completos. Vea [Comprenda las ventajas y las desventajas de los contextos de carga](#load_contexts) y [Considere la posibilidad de cambiar al contexto de carga predeterminado](#switch_to_default).  
  
 Si quiere usar el método <xref:System.Reflection.Assembly.LoadWithPartialName%2A> porque facilita la carga de ensamblados, tenga en cuenta que un error de la aplicación con un mensaje de error que identifique el ensamblado que falta es probable que proporcione una mejor experiencia de usuario que el empleo automático de una versión desconocida del ensamblado, que podría dar lugar a un comportamiento impredecible y a vulnerabilidades de seguridad.  
  
<a name="avoid_loading_into_multiple_contexts"></a>   
## <a name="avoid-loading-an-assembly-into-multiple-contexts"></a>Evite la carga de un ensamblado en varios contextos  
 La carga de un ensamblado en varios contextos puede ocasionar problemas de identidad de tipos. Si se carga el mismo tipo desde el mismo ensamblado en dos contextos diferentes, es como si se hubieran cargado dos tipos diferentes con el mismo nombre. Si intenta convertir un tipo en el otro, se produce una <xref:System.InvalidCastException> con el confuso mensaje de que no se puede convertir el tipo `MyType` en el tipo `MyType`.  
  
 Por ejemplo, imagine que se declara la interfaz `ICommunicate` en un ensamblado denominado `Utility` al que hace referencia el programa y, además, otros ensamblados que carga el programa. Estos otros ensamblados contienen tipos que implementan la interfaz `ICommunicate`, lo que permite al programa usarlos.  
  
 Ahora imagine qué ocurre al ejecutar el programa. Los ensamblados a los que hace referencia el programa se cargan en el contexto de carga predeterminado. Si carga un ensamblado de destino por su identidad, con el método <xref:System.Reflection.Assembly.Load%2A>, estará en el contexto de carga predeterminado, igual que sus dependencias. Tanto el programa como el ensamblado de destino usarán el mismo ensamblado `Utility`.  
  
 Pero imagine que carga el ensamblado de destino por su ruta de acceso, con el método <xref:System.Reflection.Assembly.LoadFile%2A>. El ensamblado se carga sin ningún contexto, así que sus dependencias no se cargan automáticamente. Podría tener un controlador para que el evento <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> proporcionara la dependencia y este podría cargar el ensamblado `Utility` sin contexto con el método <xref:System.Reflection.Assembly.LoadFile%2A>. Al crear una instancia de un tipo incluido en el ensamblado de destino e intentar asignarla a una variable de tipo `ICommunicate`, se produce una <xref:System.InvalidCastException> porque el runtime considera que las interfaces `ICommunicate` de las dos copias del ensamblado `Utility` son tipos distintos.  
  
 Hay muchos otros escenarios en los que se puede cargar un ensamblado en varios contextos. El mejor enfoque es evitar los conflictos mediante la reubicación del ensamblado de destino en la ruta de acceso de la aplicación y el empleo del método <xref:System.Reflection.Assembly.Load%2A> con el nombre para mostrar completo. Luego se carga el ensamblado en el contexto de carga predeterminado y ambos ensamblados usan el mismo ensamblado `Utility`.  
  
 Si el ensamblado de destino debe permanecer fuera de la ruta de acceso de la aplicación, puede usar el método <xref:System.Reflection.Assembly.LoadFrom%2A> para cargarlo en el contexto de origen de carga. Si el ensamblado de destino se ha compilado con una referencia al ensamblado `Utility` de la aplicación, usará el ensamblado `Utility` que la aplicación haya cargado en el contexto de carga predeterminado. Tenga en cuenta que pueden producirse problemas si el ensamblado de destino tiene una dependencia en una copia del ensamblado `Utility` ubicado fuera de la ruta de acceso de la aplicación. Si se carga ese ensamblado en el contexto de origen de carga antes de que la aplicación cargue el ensamblado `Utility`, se produce un error en la carga de la aplicación.  
  
 En la sección [Considere la posibilidad de cambiar al contexto de carga predeterminado](#switch_to_default) se explican alternativas al uso de cargas de ruta de acceso de archivo como <xref:System.Reflection.Assembly.LoadFile%2A> y <xref:System.Reflection.Assembly.LoadFrom%2A>.  
  
<a name="avoid_loading_multiple_versions"></a>   
## <a name="avoid-loading-multiple-versions-of-an-assembly-into-the-same-context"></a>Evite la carga de varias versiones de un ensamblado en el mismo contexto  
 La carga de varias versiones de un ensamblado en un contexto de carga puede producir problemas de identidad de tipos. Si se carga el mismo tipo desde dos versiones del mismo ensamblado, es como si se hubieran cargado dos tipos diferentes con el mismo nombre. Si intenta convertir un tipo en el otro, se produce una <xref:System.InvalidCastException> con el confuso mensaje de que no se puede convertir el tipo `MyType` en el tipo `MyType`.  
  
 Por ejemplo, el programa podría cargar una versión del ensamblado `Utility` directamente y luego podría cargar otro ensamblado que cargara una versión diferente del ensamblado `Utility`. O bien un error de codificación podría hacer que dos rutas de acceso de código diferentes de la aplicación cargaran versiones distintas de un ensamblado.  
  
 En el contexto de carga predeterminado, este problema puede producirse cuando se usa el método <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> y se especifican nombres para mostrar de ensamblado completos que incluyen números de versión diferentes. En el caso de los ensamblados que se cargan sin contexto, el problema puede deberse al uso del método <xref:System.Reflection.Assembly.LoadFile%2A?displayProperty=nameWithType> para cargar el mismo ensamblado desde rutas de acceso diferentes. El runtime considera que dos ensamblados que se cargan desde rutas de acceso diferentes son ensamblados distintos, aunque sus identidades sean iguales.  
  
 Además de los problemas de identidad de tipos, varias versiones de un ensamblado pueden producir una <xref:System.MissingMethodException> si un tipo cargado desde una versión del ensamblado se pasa a código que espera ese tipo desde otra versión. Por ejemplo, el código podría esperar un método que se ha agregado a la versión más reciente.  
  
 Si el comportamiento del tipo ha cambiado entre versiones, se pueden producir errores más sutiles. Por ejemplo, un método podría producir una excepción imprevista o devolver un valor inesperado.  
  
 Revise el código atentamente para garantizar que solo se cargue una versión de un ensamblado. Puede usar el método <xref:System.AppDomain.GetAssemblies%2A?displayProperty=nameWithType> para determinar qué ensamblados se cargan en un momento dado.  
  
<a name="switch_to_default"></a>   
## <a name="consider-switching-to-the-default-load-context"></a>Considere la posibilidad de cambiar al contexto de carga predeterminado  
 Examine los patrones de carga e implementación de ensamblados de la aplicación. ¿Puede eliminar ensamblados cargados desde matrices de bytes? ¿Puede mover ensamblados a la ruta de acceso de sondeo? Si los ensamblados se encuentran en la caché global de ensamblados o en la ruta de acceso de sondeo del dominio de la aplicación (es decir, su <xref:System.AppDomainSetup.ApplicationBase%2A> y <xref:System.AppDomainSetup.PrivateBinPath%2A>), puede cargar el ensamblado por su identidad.  
  
 Si no es posible colocar todos los ensamblados en la ruta de acceso de sondeo, considere alternativas como usar el modelo de complementos de .NET Framework, colocar los ensamblados en la caché global de ensamblados o crear dominios de aplicación.  
  
### <a name="consider-using-the-net-framework-add-in-model"></a>Considere la posibilidad de usar el modelo de complementos de .NET Framework  
 Si está usando el contexto de origen de carga para implementar complementos, que normalmente no están instalados en la base de la aplicación, use el modelo de complementos de .NET Framework. Este modelo proporciona aislamiento en el nivel del proceso o el dominio de la aplicación sin exigirle que administre los dominios de aplicación usted mismo. Para más información sobre el modelo de complementos, vea [Complementos y extensibilidad](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb384200(v%3dvs.100)).  
  
### <a name="consider-using-the-global-assembly-cache"></a>Considere la posibilidad de usar la caché global de ensamblados  
 Coloque los ensamblados en la caché global de ensamblados para beneficiarse de una ruta de acceso de ensamblado compartida que esté fuera de la base de la aplicación, sin perder las ventajas del contexto de carga predeterminado ni asumir las desventajas de los otros contextos.  
  
### <a name="consider-using-application-domains"></a>Considere la posibilidad de usar dominios de aplicación  
 Si determina que algunos de los ensamblados no se pueden implementar en la ruta de acceso de sondeo de la aplicación, considere la posibilidad de crear un nuevo dominio de aplicación para esos ensamblados. Use un <xref:System.AppDomainSetup> para crear el nuevo dominio de aplicación y la propiedad <xref:System.AppDomainSetup.ApplicationBase%2A?displayProperty=nameWithType> para especificar la ruta de acceso que contiene los ensamblados que quiere cargar. Si tiene varios directorios para sondear, puede establecer <xref:System.AppDomainSetup.ApplicationBase%2A> en un directorio raíz y usar la propiedad <xref:System.AppDomainSetup.PrivateBinPath%2A?displayProperty=nameWithType> para identificar los subdirectorios de sondeo. Como alternativa, puede crear varios dominios de aplicación y establecer la <xref:System.AppDomainSetup.ApplicationBase%2A> de cada dominio de aplicación en la ruta de acceso adecuada para sus ensamblados.  
  
 Tenga en cuenta que puede usar el método <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType> para cargar estos ensamblados. Dado que ahora se encuentran en la ruta de acceso de sondeo, se cargarán en el contexto de carga predeterminado en lugar de hacerlo en el contexto de origen de carga. Pero se recomienda cambiar al método <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> y proporcionar nombres para mostrar de ensamblado completos para asegurarse de que siempre se usen versiones correctas.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType>
- <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType>
- <xref:System.Reflection.Assembly.LoadFile%2A?displayProperty=nameWithType>
- <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType>
