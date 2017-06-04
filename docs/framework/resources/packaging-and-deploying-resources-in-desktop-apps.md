---
title: "Empaquetar e implementar recursos en aplicaciones de escritorio | Microsoft Docs"
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
  - "implementar aplicaciones [.NET Framework], recursos"
  - "archivos de recursos, implementar"
  - "modelo de concentrador y de radio para implementar recursos"
  - "archivos de recursos, empaquetar"
  - "recursos de la aplicación, empaquetar"
  - "ensamblado de recurso único"
  - "ensamblados satélite"
  - "referencia cultural predeterminada de aplicaciones"
  - "nombres [.NET Framework], recursos"
  - "proceso de reserva de recursos"
  - "agrupar referencias culturales"
  - "recursos de la aplicación, implementar"
  - "recursos de la aplicación, convenciones de nomenclatura"
  - "referencia cultural, empaquetar e implementar recursos"
  - "archivos de recursos, convenciones de nomenclatura"
  - "empaquetar recursos de la aplicación"
  - "recursos de aplicación, procesos de reserva"
  - "archivos de recursos, procesos de reserva"
  - "adaptar recursos"
  - "referencias culturales neutras"
ms.assetid: b224d7c0-35f8-4e82-a705-dd76795e8d16
caps.latest.revision: 26
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 26
---
# Empaquetar e implementar recursos en aplicaciones de escritorio
Las aplicaciones se basan en el administrador de recursos de .NET Framework, representado por la clase de <xref:System.Resources.ResourceManager> , para recuperar recursos localizados.  El administrador de recursos se supone que un modelo de concentrador y de radio se usa para empaquetar e implementar recursos.  El concentrador es el ensamblado principal que contiene el código ejecutable no localizable así como los recursos de una única referencia cultural, denominada referencia cultural neutra o predeterminada.  La referencia cultural predeterminada es la referencia cultural de reserva de la aplicación; es la referencia cultural cuyos utilizan recursos si los recursos localizados no pueden encontrarse.  Cada radio se conecta a un ensamblado satélite que contiene los recursos de una única referencia cultural, pero no contiene ningún código.  
  
 Este modelo ofrece varias ventajas:  
  
-   Tras implementar una aplicación, se pueden agregar de forma incremental recursos para nuevas referencias culturales.  Como el subsiguiente desarrollo de recursos específicos de la referencia cultural puede requerir mucho tiempo, esto permite lanzar primero la principal aplicación y posteriormente los recursos específicos de la referencia cultural.  
  
-   Se pueden actualizar y cambiar los ensamblados satélite de una aplicación sin recompilar dicha aplicación.  
  
-   La aplicación sólo necesita cargar aquellos ensamblados satélite que contengan los recursos necesarios para una referencia cultural determinada.  De este modo, se puede reducir en gran medida el uso de los recursos del sistema.  
  
 Sin embargo, este modelo también tiene desventajas:  
  
-   Se han de administrar varios conjuntos de recursos.  
  
-   El costo inicial de comprobar una aplicación se incrementa ya que se han de comprobar varias configuraciones.  A largo plazo, será más fácil y menos costoso comprobar una aplicación principal con varios ensamblados satélite que comprobar y mantener varias versiones internacionales paralelas.  
  
## Convenciones de nomenclatura para recursos  
 Al empaquetar los recursos de una aplicación, es preciso asignarles un nombre mediante las convenciones de nomenclatura para recursos que espera Common Language Runtime.  El tiempo de ejecución identifica un recurso por su nombre de referencia cultural.  Cada referencia cultural tiene un nombre único, que normalmente es una combinación de una dos\- letra, nombre de referencia cultural en minúscula asociado a un idioma y, si es necesario, una dos\- letra, un nombre de subreferencia asociado a un país o región.  El nombre de la subreferencia cultural va precedido del nombre de la referencia cultural, separados ambos nombres por un guión \(\-\).  Incluyen ja\- JP de ejemplos para el japonés de Japón, en\-us para el inglés de Estados Unidos, de\- DE para alemán de Alemania, o de\- ON para el alemán de Austria.  Vea [Referencia de la API de \(NLS\) de la compatibilidad con el idioma nacional](http://go.microsoft.com/fwlink/?LinkId=200048) en el centro para desarrolladores de Global de ir para una lista completa de los nombres de referencia cultural.  
  
> [!NOTE]
>  Para obtener información sobre cómo crear archivos de recursos, vea [Crear archivos de recursos](../../../docs/framework/resources/creating-resource-files-for-desktop-apps.md) y [Crear ensamblados satélite](../../../docs/framework/resources/creating-satellite-assemblies-for-desktop-apps.md) en MSDN Library.  
  
<a name="cpconpackagingdeployingresourcesanchor1"></a>   
## El proceso de reserva de recursos  
 El modelo de concentrador y de radio para empaquetar e implementar recursos utiliza un proceso de reserva para buscar los recursos apropiados.  Si una aplicación solicita un recurso localizado que no esté disponible, Common Language Runtime busca la jerarquía de las referencias culturales para un recurso de reserva apropiado que más estrechamente la solicitud de la aplicación de usuario, y produce una excepción sólo como último recurso.  Si encuentra un recurso apropiado, el motor en tiempo de ejecución lo utilizará en cada nivel de la jerarquía.  En caso de que no lo encuentre, la búsqueda continuará en el siguiente nivel.  
  
 Para mejorar el rendimiento de la búsqueda, aplique el atributo <xref:System.Resources.NeutralResourcesLanguageAttribute> al ensamblado principal y pásele el nombre del idioma neutro que funcionará con el ensamblado principal neutral.  
  
> [!TIP]
>  Puede utilizar el elemento de configuración de [\<relativeBindForResources\>](../../../docs/framework/configure-apps/file-schema/runtime/relativebindforresources-element.md) para optimizar el proceso de reserva de recursos y el proceso por el que el motor en tiempo de ejecución para los ensamblados de recursos.  Para obtener más información, vea la sección de [Optimizar el proceso de reserva de recursos](../../../docs/framework/resources/packaging-and-deploying-resources-in-desktop-apps.md#Optimizing) .  
  
 El recurso que es el proceso de reserva implica los pasos siguientes:  
  
1.  El tiempo de ejecución comprueba primero [caché global de ensamblados](../../../docs/framework/app-domains/gac.md) para un ensamblado que coincida con la referencia cultural solicitada para la aplicación.  
  
     La caché global de ensamblados puede almacenar ensamblados de recursos que compartan numerosas aplicaciones.  De este modo, no es preciso incluir conjuntos de recursos específicos en la estructura de directorios de cada aplicación que se cree.  Si el motor en tiempo de ejecución encuentra una referencia a un ensamblado, buscará el recurso solicitado en dicho ensamblado.  Si encuentra la entrada en el ensamblado, utilizará el recurso solicitado.  En caso contrario, continuará la búsqueda.  
  
2.  El tiempo de ejecución después en tiempo de ejecución que se ejecuta actualmente un directorio que coincida con la referencia cultural solicitada.  Si lo encuentra, buscará en ese directorio un ensamblado satélite válido para la referencia cultural solicitada.  Después, el motor en tiempo de ejecución busca el recurso solicitado en el ensamblado satélite.  Si lo encuentra en el ensamblado, lo utilizará.  En caso contrario, continuará la búsqueda.  
  
3.  Las siguientes consultas en tiempo de ejecución Windows Installer para determinar si el ensamblado satélite debe instalarse a petición.  Si es así controla la instalación, carga el ensamblado, y busca el o el recurso solicitado.  Si lo encuentra en el ensamblado, lo utilizará.  En caso contrario, continuará la búsqueda.  
  
4.  El runtime genera el evento de <xref:System.AppDomain.AssemblyResolve?displayProperty=fullName> para indicar que no encuentra el ensamblado satélite.  Si elige para controlar el evento, el controlador puede devolver una referencia al ensamblado satélite cuyos utilizará recursos para la búsqueda.  Si no, el controlador de eventos devuelve `null` y la búsqueda continuará.  
  
5.  El tiempo de ejecución busca la caché global de ensamblados de nuevo, esta vez para el ensamblado principal de la referencia cultural solicitada.  Si existe, el motor en tiempo de ejecución buscará el recurso solicitado en el ensamblado.  
  
     La referencia cultural primaria se define como la referencia cultural de reserva adecuada.  Considere los ensamblados primarios como candidatos de reserva, porque proporcionar cualquier recurso es preferible a producir una excepción.  Este proceso permite asimismo volver a utilizar los recursos.  Debe incluir un recurso determinado en el nivel primario si la referencia cultural secundaria no necesita localizar el recurso solicitado.  Por ejemplo, si proporciona los ensamblados satélite para en \(inglés neutro\), en\- GB \(inglés del Reino Unido\), y en\-us \(inglés de Estados Unidos\), el satélite de en contendrá la terminología común, y satélites de en\- GB y en\-us pueden proporcionar reemplazan únicamente en los términos diferentes.  
  
6.  A continuación, el motor en tiempo de ejecución comprueba si el directorio del ensamblado que se ejecuta actualmente contiene un directorio primario.  Si existe un directorio primario, el motor en tiempo de ejecución buscará en ese directorio un ensamblado satélite válido para la referencia cultural primaria.  Si encuentra el ensamblado, buscará el recurso solicitado en dicho ensamblado.  Si encuentra el recurso, lo utilizará.  En caso contrario, continuará la búsqueda.  
  
7.  Las siguientes consultas en tiempo de ejecución Windows Installer para determinar si el ensamblado satélite primario debe instalarse a petición.  Si es así controla la instalación, carga el ensamblado, y busca el o el recurso solicitado.  Si lo encuentra en el ensamblado, lo utilizará.  En caso contrario, continuará la búsqueda.  
  
8.  El runtime genera el evento de <xref:System.AppDomain.AssemblyResolve?displayProperty=fullName> para indicar que no se puede encontrar un recurso de reserva apropiado.  Si elige para controlar el evento, el controlador puede devolver una referencia al ensamblado satélite cuyos utilizará recursos para la búsqueda.  Si no, el controlador de eventos devuelve `null` y la búsqueda continuará.  
  
9. El tiempo de ejecución busca los ensamblados primarios, como en los tres pasos anteriores, en varios posibles niveles.  Cada referencia cultural tiene sólo un elemento primario, definido por la propiedad de <xref:System.Globalization.CultureInfo.Parent%2A?displayProperty=fullName> , pero éste puede tener su propio elemento primario.  La búsqueda de las referencias culturales principales se detiene cuando la propiedad de <xref:System.Globalization.CultureInfo.Parent%2A> de una referencia cultural devuelve <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=fullName>; para la reserva de recursos, la referencia cultural no se considera una referencia cultural primaria o una referencia cultural que puedan tener recursos.  
  
10. Si se han buscado la referencia cultural inicialmente especificada y todos los ensamblados primarios pero aún no se ha encontrado el recurso, se utilizará el recurso correspondiente a la referencia cultural \(de reserva\) predeterminada.  Normalmente, se incluyen recursos para la referencia cultural predeterminada del ensamblado de la aplicación principal.  Sin embargo, puede especificar un valor de <xref:System.Resources.UltimateResourceFallbackLocation> para la propiedad de <xref:System.Resources.NeutralResourcesLanguageAttribute.Location%2A> de <xref:System.Resources.NeutralResourcesLanguageAttribute> para indicar que la ubicación de los recursos de reserva definitivos es un ensamblado satélite, en lugar del ensamblado principal.  
  
    > [!NOTE]
    >  El recurso predeterminado es el único recurso que puede compilarse con el ensamblado principal.  A menos que especifique un ensamblado satélite utilizando el atributo de <xref:System.Resources.NeutralResourcesLanguageAttribute> , es el último reserva \(elemento primario final\).  Por consiguiente, recomendamos que incluya siempre un conjunto predeterminado de recursos en el ensamblado principal.  Esto ayuda a evitar que las excepciones se producen.  Al incluir un archivo de recursos predeterminado, se proporciona una reserva de todos los recursos y se garantiza que siempre habrá al menos un recurso para el usuario, aunque no sea específico de una referencia cultural.  
  
11. Finalmente, si el runtime no encuentra un recurso para una referencia cultural \(de reserva\) predeterminada, una excepción de <xref:System.Resources.MissingManifestResourceException> o de <xref:System.Resources.MissingSatelliteAssemblyException> se produce para indicar que no se ha encontrado el recurso.  
  
 Por ejemplo, suponga que las solicitudes de la aplicación que un recurso localizado para español \(México\) \(la referencia cultural es\- MX\).  El tiempo de ejecución busca primero en la caché global de ensamblados para el ensamblado que coincida con es\- MX, pero no lo encuentra.  El tiempo de ejecución busca en el directorio del ensamblado que se ejecuta actualmente un directorio es\- MX.  Al no encontrarlo, el tiempo de ejecución busca el nuevo en la caché global de ensamblados un ensamblado primario que refleje la referencia cultural de reserva apropiada en este caso, es \(español\).  Si no encuentra el ensamblado primario, el tiempo de ejecución busca todos los posibles niveles de ensamblados primarios para la referencia cultural es\- MX hasta que encuentra un recurso correspondiente.  Si no lo encuentra, el tiempo de ejecución utilizará el recurso para la referencia cultural predeterminada.  
  
<a name="Optimizing"></a>   
### Optimizar el proceso de reserva de recursos  
 En las siguientes condiciones, puede optimizar el proceso por el que el tiempo de ejecución busca los recursos en ensamblados satélite  
  
-   Implementan los ensamblados satélite en la misma ubicación que el ensamblado del código.  Si el ensamblado de código está instalado en [Caché global de ensamblados](../../../docs/framework/app-domains/gac.md), los ensamblados satélite también se instalan en la caché global de ensamblados.  Si el ensamblado de código está instalado en un directorio, los ensamblados satélite se instalan en carpetas cultura\- específicas de ese directorio.  
  
-   Los ensamblados satélite no se instalan a petición.  
  
-   El código de aplicación no controla el evento de <xref:System.AppDomain.AssemblyResolve?displayProperty=fullName> .  
  
 Se optimiza el buscar ensamblados satélite incluido el elemento de [\<relativeBindForResources\>](../../../docs/framework/configure-apps/file-schema/runtime/relativebindforresources-element.md) y estableciendo el atributo de `enabled` a `true` en el archivo de configuración de la aplicación, como se muestra en el ejemplo siguiente.  
  
```  
  
<configuration>  
   <runtime>  
      <relativeBindForResources enabled="true" />  
   </runtime>  
</configuration>  
  
```  
  
 El sondeo optimizado para los ensamblados satélite es una característica de pertenencia.  Es decir, el tiempo de ejecución sigue los pasos documentados en [El proceso de reserva de recursos](../../../docs/framework/resources/packaging-and-deploying-resources-in-desktop-apps.md#cpconpackagingdeployingresourcesanchor1) a menos que el elemento de [\<relativeBindForResources\>](../../../docs/framework/configure-apps/file-schema/runtime/relativebindforresources-element.md) esté presente en el archivo de configuración de la aplicación y su atributo de `enabled` se establece en `true`.  Si es así, el proceso de búsqueda para un ensamblado satélite se modifica como sigue:  
  
-   El tiempo de ejecución utiliza la ubicación del ensamblado de código principal debe buscar el ensamblado satélite.  Si el ensamblado primario está instalado en la caché global de ensamblados, el motor en tiempo de ejecución en caché pero no en el directorio de la aplicación.  Si el ensamblado primario está instalado en un directorio de aplicaciones, el motor en tiempo de ejecución en el directorio de aplicaciones pero no en la caché global de ensamblados.  
  
-   El runtime no consulta Windows Installer para instalación a petición de ensamblados satélite.  
  
-   Si el sondeo para un ensamblado determinado de recursos, el runtime no provoca el evento de <xref:System.AppDomain.AssemblyResolve?displayProperty=fullName> .  
  
### Recursos de reserva definitivos en el ensamblado satélite  
 Puede quitar recursos del ensamblado principal y especificar opcionalmente que el tiempo de ejecución debe cargar a los recursos de reserva de un ensamblado satélite que corresponde a una referencia cultural concreta.  Para controlar el proceso de reserva, se utiliza el constructor de <xref:System.Resources.NeutralResourcesLanguageAttribute.%23ctor%28System.String%2CSystem.Resources.UltimateResourceFallbackLocation%29?displayProperty=fullName> y proporcione un valor para el parámetro de <xref:System.Resources.UltimateResourceFallbackLocation> que especifica si el administrador de recursos debe extraer los recursos de reserva del ensamblado principal o un ensamblado satélite.  
  
 El ejemplo siguiente se usa el atributo de <xref:System.Resources.NeutralResourcesLanguageAttribute> para almacenar los recursos de reserva de una aplicación en un ensamblado satélite para el idioma francés de \(fr\).  El ejemplo tiene dos archivos de recursos basados en texto que definen un solo recurso de cadena denominado `Greeting`.  El primer, resources.fr.txt, contiene un recurso de idioma francés.  
  
```  
Greeting=Bon jour!  
```  
  
 El segundo, recursos, ru.txt, contiene un recurso de lenguaje ruso.  
  
```  
Greeting=Добрый день  
```  
  
 Estos dos archivos estén creados a los archivos .resources ejecutando [generador de archivos de recursos \(Resgen.exe\)](../../../docs/framework/tools/resgen-exe-resource-file-generator.md) desde la línea de comandos.  Para el recurso de idioma francés, el comando es:  
  
 **resgen.exe resources.fr.txt**  
  
 Para el recurso de idioma ruso, el comando es:  
  
 **resgen.exe resources.ru.txt**  
  
 Los archivos .resources son insertados en bibliotecas de vínculos dinámicos ejecutando [el vinculador del ensamblado \(Al.exe\)](../../../docs/framework/tools/al-exe-assembly-linker.md) de la línea de comandos para el recurso de idioma francés como sigue:  
  
 **al \/t:lib \/embed:resources.fr.resources \/culture:fr \/out:fr\\Example1.resources.dll**  
  
 y para el recurso de idioma ruso como sigue:  
  
 **al \/t:lib \/embed:resources.ru.resources \/culture:ru \/out:ru\\Example1.resources.dll**  
  
 El código fuente de la aplicación reside en un archivo denominado Example1.cs o Example1.vb.  Incluye el atributo de <xref:System.Resources.NeutralResourcesLanguageAttribute> para indicar que el recurso de la aplicación está en el subdirectorio fr.  Crea una instancia del administrador de recursos, recupera el valor del recurso de `Greeting` , y lo muestra en la consola.  
  
 [!code-csharp[Conceptual.Resources.Packaging#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.resources.packaging/cs/example1.cs#1)]
 [!code-vb[Conceptual.Resources.Packaging#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.resources.packaging/vb/example1.vb#1)]  
  
 Puede compilar el código fuente de C\# desde la línea de comandos como sigue:  
  
 **csc Example1.cs**  
  
 El comando del compilador de Visual Basic es muy similar:  
  
 **vbc Example1.vb**  
  
 Porque no hay recursos incrustados en el ensamblado principal, no tiene que compilar utilizando el modificador `/resource` .  
  
 Al ejecutar el ejemplo de un sistema cuyo idioma es algo distinto de ruso, genera el siguiente resultado:  
  
```  
Bon jour!  
```  
  
## Sugerencia de alternativa de empaquetado  
 Restricciones de tiempo o presupuestarias pueden impedir que se cree un conjunto de recursos para cada subreferencia cultural que admite la aplicación.  En su lugar, puede crear un único ensamblado satélite para una referencia cultural primaria que todos las subreferencias culturales relacionadas pueden utilizar.  Por ejemplo, puede proporcionar un único ensamblado satélite inglés \(en\) que sea recuperado por usuarios que soliciten recursos en inglés específicos de la región, y un único ensamblado satélite en alemán \(de\) para usuarios que soliciten recursos alemán específicos de la región.  Por ejemplo, las solicitudes de alemán de Alemania \(de\- DE\), Austria \(de\- IN\), y Suiza \(de\- CH\) recurrirán al ensamblado satélite en alemán \(de\).  Los recursos predeterminados constituyen la reserva final y por consiguiente deben ser los recursos que se solicitados por la mayoría de los usuarios de la aplicación, por lo que elija a estos recursos cuidadosamente.  Este enfoque implementa los recursos que menos cultural específico, pero puede reducir significativamente los costos de localización de la aplicación.  
  
## Vea también  
 [Recursos de aplicaciones de escritorio](../../../docs/framework/resources/index.md)   
 [Caché global de ensamblados](../../../docs/framework/app-domains/gac.md)   
 [Crear archivos de recursos](../../../docs/framework/resources/creating-resource-files-for-desktop-apps.md)   
 [Crear ensamblados satélite](../../../docs/framework/resources/creating-satellite-assemblies-for-desktop-apps.md)