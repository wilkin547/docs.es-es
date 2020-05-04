---
title: Empaquetado e implementación de recursos en aplicaciones .NET
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- deploying applications [.NET Framework], resources
- resource files, deploying
- hub-and-spoke resource deployment model
- resource files, packaging
- application resources, packaging
- single resource assembly
- satellite assemblies
- default culture for applications
- names [.NET Framework], resources
- fallback process for resources
- grouping cultures
- application resources, deploying
- application resources, naming conventions
- culture, packaging and deploying resources
- resource files, naming conventions
- packaging application resources
- application resources, fallback processes
- resource files, fallback processes
- localizing resources
- neutral cultures
ms.assetid: b224d7c0-35f8-4e82-a705-dd76795e8d16
ms.openlocfilehash: d64e3b5201e34541fdafa5724b0c7e8c3f6c0c0d
ms.sourcegitcommit: 7980a91f90ae5eca859db7e6bfa03e23e76a1a50
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/13/2020
ms.locfileid: "81243055"
---
# <a name="packaging-and-deploying-resources-in-net-apps"></a>Empaquetado e implementación de recursos en aplicaciones .NET

Las aplicaciones se basan en el Administrador de recursos de .NET Framework, representado por la clase <xref:System.Resources.ResourceManager>, para recuperar recursos localizados. El Administrador de recursos da por supuesto que se usa un modelo de concentrador y radio para empaquetar e implementar los recursos. El concentrador es el ensamblado principal que contiene el código ejecutable no localizable y los recursos de una referencia cultural única, denominada referencia cultural neutra o predeterminada. La referencia cultural predeterminada es la referencia cultural de reserva de la aplicación. Se trata de la referencia cultural cuyos recursos se usarán si no se encuentran recursos localizados. Cada radio se conecta a un ensamblado satélite que contiene los recursos de una única referencia cultural, pero no contiene código.

Este modelo cuenta con varias ventajas:

- Puede agregar recursos para nuevas referencias culturales de forma incremental después de implementar una aplicación. Dado que el desarrollo posterior de los recursos específicos de la referencia cultural puede requerir bastante tiempo, esto permite lanzar primero la aplicación principal y entregar los recursos específicos de la referencia cultural en un momento posterior.
- Puede actualizar y cambiar los ensamblados satélite de una aplicación sin volver a compilarla.
- Una aplicación solo necesita cargar los ensamblados satélite que contienen los recursos necesarios para una referencia cultural determinada. Esto puede reducir considerablemente el uso de recursos del sistema.

 Aun así, este modelo también tiene inconvenientes:

- Debe administrar varios conjuntos de recursos.
- El costo inicial de probar una aplicación es mayor, ya que se deben someter a prueba varias configuraciones. Tenga en cuenta que, a largo plazo, será más fácil y menos costoso probar una aplicación principal con varios ensamblados satélite que probar y mantener varias versiones internacionales paralelas.

## <a name="resource-naming-conventions"></a>Convenciones de nomenclatura de recursos

Al empaquetar los recursos de la aplicación, debe asignarles un nombre según las convenciones de nomenclatura de recursos que espera Common Language Runtime. El tiempo de ejecución identifica un recurso por su nombre de referencia cultural. Cada referencia cultural tiene un nombre único, que suele ser una combinación de un nombre de referencia cultural de dos letras en minúsculas asociado a un idioma y, si es necesario, un nombre de referencia cultural secundaria de dos letras en mayúsculas asociado a un país o región. El nombre de la referencia cultural secundaria va después del nombre de la referencia cultural, separado por un guion (-). Algunos ejemplos son los siguientes: ja-JP para japonés de Japón, en-US para inglés de Estados Unidos, de-DE para alemán de Alemania o de-AT para alemán de Austria. Consulte la columna **Etiqueta de idioma** en la [lista de nombres de los idiomas y las regiones compatibles con Windows](https://docs.microsoft.com/openspecs/windows_protocols/ms-lcid/a9eac961-e77d-41a6-90a5-ce1a8b0cdb9c). Los nombres de las referencias culturales siguen el estándar definido por [BCP 47](https://tools.ietf.org/html/bcp47).

> [!NOTE]
> Existen algunas excepciones relativas a los nombres de referencia cultural de dos letras, como `zh-Hans` en el caso del chino (simplificado).

> [!NOTE]
> Para más información sobre cómo crear archivos de recursos, vea [Crear archivos de recursos](creating-resource-files-for-desktop-apps.md) y [Crear ensamblados satélite](creating-satellite-assemblies-for-desktop-apps.md).

<a name="cpconpackagingdeployingresourcesanchor1"></a>

## <a name="the-resource-fallback-process"></a>El proceso de reserva de recursos

El modelo de concentrador y radio para empaquetar e implementar recursos usa un proceso de reserva para buscar los recursos apropiados. Si una aplicación solicita un recurso localizado que no está disponible, Common Language Runtime busca en la jerarquía de referencias culturales el recurso de reserva apropiado que coincida mejor con la solicitud de la aplicación del usuario y produce una excepción solo en última instancia. El tiempo de ejecución usará el recurso apropiado, si lo encuentra, en cada nivel de la jerarquía. Si no se encuentra el recurso, la búsqueda continúa en el siguiente nivel.

Para mejorar el rendimiento de la búsqueda, aplique el atributo <xref:System.Resources.NeutralResourcesLanguageAttribute> al ensamblado principal y pásele el nombre del idioma neutral que funcionará con el ensamblado principal.

### <a name="net-framework-resource-fallback-process"></a>Proceso de reserva de recursos de .NET Framework

El proceso de reserva de recursos de .NET Framework conlleva los pasos siguientes:

> [!TIP]
> Es posible que pueda usar el elemento de configuración [\<relativeBindForResources>](../configure-apps/file-schema/runtime/relativebindforresources-element.md) para optimizar el proceso de reserva de recursos y el proceso mediante el cual el tiempo de ejecución sondea los ensamblados de recursos. Para obtener más información, vea la sección [Optimizar el proceso de reserva de recursos](packaging-and-deploying-resources-in-desktop-apps.md#Optimizing).

1. El tiempo de ejecución busca primero en la [caché global de ensamblados](../app-domains/gac.md) un ensamblado que coincida con la referencia cultural solicitada para la aplicación.

     La caché global de ensamblados puede almacenar ensamblados de recursos compartidos por varias aplicaciones. Esto evita tener que incluir conjuntos de recursos específicos en la estructura de directorios de cada aplicación que se cree. Si el tiempo de ejecución encuentra una referencia al ensamblado, busca en el ensamblado el recurso solicitado. Si encuentra la entrada en el ensamblado, usará el recurso solicitado. Si no encuentra la entrada, seguirá con la búsqueda.

2. Después, el tiempo de ejecución busca en el directorio del ensamblado actualmente en ejecución un subdirectorio que coincida con la referencia cultural solicitada. Si lo encuentra, busca en ese subdirectorio un ensamblado satélite válido para la referencia cultural solicitada. Luego, el tiempo de ejecución busca en el ensamblado satélite el recurso solicitado. Si encuentra el recurso en el ensamblado, lo usará. Si no encuentra el recurso, seguirá con la búsqueda.

3. Después, el tiempo de ejecución consulta Windows Installer para determinar si el ensamblado satélite se va a instalar a petición. Si es así, controla la instalación, carga el ensamblado y busca en él el recurso solicitado. Si encuentra el recurso en el ensamblado, lo usará. Si no encuentra el recurso, seguirá con la búsqueda.

4. El tiempo de ejecución genera el evento <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> para indicar que no ha podido encontrar el ensamblado satélite. Si opta por controlar el evento, el controlador de eventos puede devolver una referencia al ensamblado satélite cuyos recursos se usarán para la búsqueda. En caso contrario, el controlador de eventos devuelve `null` y continúa la búsqueda.

5. Luego, el tiempo de ejecución busca de nuevo en la caché global de ensamblados el ensamblado principal de la referencia cultural solicitada. Si el ensamblado principal existe en la caché global de ensamblados, el tiempo de ejecución busca en el ensamblado el recurso solicitado.

     La referencia cultural principal se define como la referencia cultural de reserva adecuada. Considere los elementos principales como candidatos de reserva, porque es preferible proporcionar cualquier recurso antes que producir una excepción. Este proceso también permite reutilizar los recursos. Debe incluir un recurso determinado en el nivel principal solo si la referencia cultural secundaria no necesita localizar el recurso solicitado. Por ejemplo, si proporciona ensamblados satélite para `en` (inglés neutro), `en-GB` (inglés del Reino Unido) y `en-US` (inglés de Estados Unidos), el satélite `en` contendrá la terminología común, mientras que los satélites `en-GB` y `en-US` proporcionarán invalidaciones solo para los términos que difieren.

6. Después, el tiempo de ejecución busca en el directorio del ensamblado actualmente en ejecución para ver si contiene un directorio principal. Si existe un directorio principal, el tiempo de ejecución busca en el directorio un ensamblado satélite válido para la referencia cultural principal. Si encuentra el ensamblado, el tiempo de ejecución busca en el ensamblado el recurso solicitado. Si encuentra el recurso, lo usará. Si no encuentra el recurso, seguirá con la búsqueda.

7. Después, el tiempo de ejecución consulta Windows Installer para determinar si el ensamblado satélite principal se va a instalar a petición. Si es así, controla la instalación, carga el ensamblado y busca en él el recurso solicitado. Si encuentra el recurso en el ensamblado, lo usará. Si no encuentra el recurso, seguirá con la búsqueda.

8. El tiempo de ejecución genera el evento <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> para indicar que no ha podido encontrar un recurso de reserva apropiado. Si opta por controlar el evento, el controlador de eventos puede devolver una referencia al ensamblado satélite cuyos recursos se usarán para la búsqueda. En caso contrario, el controlador de eventos devuelve `null` y continúa la búsqueda.

9. Después, el tiempo de ejecución busca ensamblados principales, como en los tres pasos anteriores, en varios niveles posibles. Cada referencia cultural tiene un solo elemento principal, que se define mediante la propiedad <xref:System.Globalization.CultureInfo.Parent%2A?displayProperty=nameWithType>, pero un elemento principal puede tener su propio elemento principal. La búsqueda de referencias culturales principales se detiene cuando la propiedad <xref:System.Globalization.CultureInfo.Parent%2A> de una referencia cultural devuelve <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=nameWithType>. Para la reserva de recursos, la referencia cultural invariable no se considera una referencia cultural principal ni una referencia cultural que pueda tener recursos.

10. Si se ha buscado en la referencia cultural especificada inicialmente y en todos los elementos principales y el recurso sigue sin encontrarse, se usa el recurso de la referencia cultural predeterminada (de reserva). Normalmente, los recursos de la referencia cultural predeterminada se incluyen en el ensamblado de la aplicación principal. Aun así, puede especificar un valor de <xref:System.Resources.UltimateResourceFallbackLocation.Satellite> para la propiedad <xref:System.Resources.NeutralResourcesLanguageAttribute.Location%2A> del atributo <xref:System.Resources.NeutralResourcesLanguageAttribute> para indicar que la ubicación de reserva definitiva para los recursos es un ensamblado satélite, en lugar del ensamblado principal.

    > [!NOTE]
    > El recurso predeterminado es el único recurso que se puede compilar con el ensamblado principal. A menos que especifique un ensamblado satélite mediante el atributo <xref:System.Resources.NeutralResourcesLanguageAttribute>, es la reserva definitiva (elemento principal final). Por lo tanto, se recomienda incluir siempre un conjunto de recursos predeterminado en el ensamblado principal. Esto ayuda a evitar que se produzcan excepciones. Al incluir un archivo de recursos predeterminado, se proporciona una reserva para todos los recursos y se garantiza que al menos un recurso esté siempre presente para el usuario, incluso si no es específico de la referencia cultural.

11. Por último, si el tiempo de ejecución no encuentra un recurso para una referencia cultural predeterminada (de reserva), se produce una excepción <xref:System.Resources.MissingManifestResourceException> o <xref:System.Resources.MissingSatelliteAssemblyException> para indicar que no se pudo encontrar el recurso.

Por ejemplo, supongamos que la aplicación solicita un recurso localizado para español (México) (referencia cultural `es-MX`). El tiempo de ejecución busca primero en la caché global de ensamblados el ensamblado que coincida con `es-MX`, pero no lo encuentra. Después, el tiempo de ejecución busca un directorio `es-MX` en el directorio del ensamblado actualmente en ejecución. Si esto no funciona, el tiempo de ejecución busca de nuevo en la caché global de ensamblados un ensamblado principal que refleje la referencia cultural de reserva adecuada, en este caso, `es` (español). Si no se encuentra el ensamblado principal, el tiempo de ejecución busca en todos los posibles niveles de ensamblados principales la referencia cultural `es-MX` hasta que encuentra un recurso correspondiente. Si no se encuentra un recurso, el tiempo de ejecución usa el recurso para la referencia cultural predeterminada.

<a name="Optimizing"></a>

#### <a name="optimizing-the-net-framework-resource-fallback-process"></a>Optimización del proceso de reserva de recursos de .NET Framework

En las siguientes condiciones, puede optimizar el proceso por el que el tiempo de ejecución busca recursos en ensamblados satélite.

- Los ensamblados satélite se implementan en la misma ubicación que el ensamblado de código. Si el ensamblado de código está instalado en la [caché global de ensamblados](../app-domains/gac.md), los ensamblados satélite también se instalan en la caché global de ensamblados. Si el ensamblado de código está instalado en un directorio, los ensamblados satélite se instalan en carpetas específicas de referencias culturales de ese directorio.

- Los ensamblados satélite no se instalan a petición.

- El código de la aplicación no controla el evento <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType>.

Para optimizar el sondeo de ensamblados satélite, incluya el elemento [\<relativeBindForResources>](../configure-apps/file-schema/runtime/relativebindforresources-element.md) y establezca su atributo `enabled` en `true` en el archivo de configuración de la aplicación, como se muestra en el ejemplo siguiente.

```xml
<configuration>
   <runtime>
      <relativeBindForResources enabled="true" />
   </runtime>
</configuration>
```

El sondeo optimizado de los ensamblados satélite es una característica opcional. Es decir, el tiempo de ejecución sigue los pasos documentados en [El proceso de reserva de recursos](packaging-and-deploying-resources-in-desktop-apps.md#cpconpackagingdeployingresourcesanchor1), a menos que el elemento [\<relativeBindForResources>](../configure-apps/file-schema/runtime/relativebindforresources-element.md) esté presente en el archivo de configuración de la aplicación y su atributo `enabled` esté establecido en `true`. Si este es el caso, el proceso de sondeo de un ensamblado satélite se modifica de la manera siguiente:

- El tiempo de ejecución usa la ubicación del ensamblado de código principal para sondear el ensamblado satélite. Si el ensamblado principal está instalado en la caché global de ensamblados, el tiempo de ejecución sondea la memoria caché, pero no el directorio de la aplicación. Si el ensamblado principal está instalado en un directorio de aplicación, el tiempo de ejecución sondea el directorio de la aplicación, pero no la caché global de ensamblados.

- El tiempo de ejecución no consulta Windows Installer para la instalación a petición de ensamblados satélite.

- Si se produce un error en el sondeo de un ensamblado de recurso en particular, el tiempo de ejecución no genera el evento <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType>.

### <a name="net-core-resource-fallback-process"></a>Proceso de reserva de recursos de .NET Core

El proceso de reserva de recursos de .NET Core conlleva los pasos siguientes:

1. El entorno de ejecución intenta cargar un ensamblado satélite para la referencia cultural solicitada.
     - Busca en el directorio del ensamblado actualmente en ejecución un directorio que coincida con la referencia cultural solicitada. Si lo encuentra, busca en ese directorio un ensamblado satélite válido para la referencia cultural solicitada y lo carga.

       > [!NOTE]
       > En sistemas operativos con sistemas de archivos que distinguen mayúsculas de minúsculas (es decir, Linux y macOS), la búsqueda del subdirectorio de nombres de referencias culturales distingue mayúsculas de minúsculas. El nombre del subdirectorio debe coincidir exactamente con las mayúsculas y minúsculas de <xref:System.Globalization.CultureInfo.Name?displayProperty=nameWithType> (por ejemplo, `es` o `es-MX`).

       > [!NOTE]
       > Si el programador ha derivado un contexto local de ensamblado personalizado de <xref:System.Runtime.Loader.AssemblyLoadContext>, la situación es complicada. Si el ensamblado que se ejecuta se cargó en el contexto personalizado, el entorno de ejecución carga el ensamblado satélite en el contexto personalizado. Los detalles quedan fuera del ámbito de este documento. Consulte <xref:System.Runtime.Loader.AssemblyLoadContext>.

     - Si no se encuentra un ensamblado satélite, <xref:System.Runtime.Loader.AssemblyLoadContext> genera el evento <xref:System.Runtime.Loader.AssemblyLoadContext.Resolving?displayProperty=nameWithType> para indicar que no se puede encontrarlo. Si opta por controlar el evento, el controlador de eventos puede cargar y devolver una referencia al ensamblado satélite.
     - Si todavía no se encuentra un ensamblado satélite, AssemblyLoadContext hace que AppDomain desencadene un evento <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> para indicar que no es posible encontrar el ensamblado satélite. Si opta por controlar el evento, el controlador de eventos puede cargar y devolver una referencia al ensamblado satélite.

2. Si se encuentra un ensamblado satélite, el entorno de ejecución lo busca para el recurso solicitado. Si encuentra el recurso en el ensamblado, lo usará. Si no encuentra el recurso, seguirá con la búsqueda.

     > [!NOTE]
     > Para buscar un recurso dentro del ensamblado satélite, el entorno de ejecución busca el archivo de recursos solicitado por <xref:System.Resources.ResourceManager> para el <xref:System.Globalization.CultureInfo.Name?displayProperty=nameWithType> actual. Dentro del archivo de recursos, busca el nombre del recurso solicitado. Si no se encuentra ninguno, se considera que no se encontró el recurso.

3. A continuación, el entorno de ejecución busca los ensamblados de referencias culturales principales a través de muchos niveles potenciales, y repite cada vez los pasos 1 y 2.

     La referencia cultural principal se define como una referencia cultural de reserva adecuada. Considere los elementos principales como candidatos de reserva, porque es preferible proporcionar cualquier recurso antes que producir una excepción. Este proceso también permite reutilizar los recursos. Debe incluir un recurso determinado en el nivel principal solo si la referencia cultural secundaria no necesita localizar el recurso solicitado. Por ejemplo, si proporciona ensamblados satélite para `en` (inglés neutro), `en-GB` (inglés del Reino Unido) y `en-US` (inglés de Estados Unidos), el satélite `en` contiene la terminología común, mientras que los satélites `en-GB` y `en-US` proporcionarán invalidaciones solo para los términos que difieren.

     Cada referencia cultural tiene un solo elemento principal, que se define mediante la propiedad <xref:System.Globalization.CultureInfo.Parent%2A?displayProperty=nameWithType>, pero un elemento principal puede tener su propio elemento principal. La búsqueda de las referencias culturales principales se detiene cuando la propiedad <xref:System.Globalization.CultureInfo.Parent%2A> de una referencia cultural devuelve <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=nameWithType>. Para la reserva de recursos, la referencia cultural invariable no se considera como una referencia cultural principal ni como una referencia cultural que puede tener recursos.

4. Si se ha buscado en la referencia cultural especificada inicialmente y en todos los elementos principales y el recurso sigue sin encontrarse, se usa el recurso de la referencia cultural predeterminada (de reserva). Normalmente, los recursos de la referencia cultural predeterminada se incluyen en el ensamblado de la aplicación principal. Aun así, puede especificar un valor de <xref:System.Resources.UltimateResourceFallbackLocation.Satellite?displayProperty.nameWithType> para la propiedad <xref:System.Resources.NeutralResourcesLanguageAttribute.Location%2A> para indicar que la ubicación de reserva definitiva para los recursos es un ensamblado satélite, en lugar del ensamblado principal.

    > [!NOTE]
    > El recurso predeterminado es el único recurso que se puede compilar con el ensamblado principal. A menos que especifique un ensamblado satélite mediante el atributo <xref:System.Resources.NeutralResourcesLanguageAttribute>, es la reserva definitiva (elemento principal final). Por lo tanto, se recomienda incluir siempre un conjunto de recursos predeterminado en el ensamblado principal. Esto ayuda a evitar que se produzcan excepciones. Al incluir un archivo de recursos predeterminado, se proporciona una reserva para todos los recursos y se garantiza que al menos un recurso esté siempre presente para el usuario, incluso si no es específico de la referencia cultural.

5. Por último, si el tiempo de ejecución no encuentra un archivo de recursos para una referencia cultural predeterminada (de reserva), se produce una excepción <xref:System.Resources.MissingManifestResourceException> o <xref:System.Resources.MissingSatelliteAssemblyException> para indicar que no se pudo encontrar el recurso. Si se encuentra el archivo de recursos pero el recurso solicitado no se encuentra, la solicitud devuelve `null`.

### <a name="ultimate-fallback-to-satellite-assembly"></a>Reserva definitiva en ensamblado satélite

Como alternativa, puede quitar recursos del ensamblado principal y especificar que el tiempo de ejecución debe cargar los recursos de reserva definitiva de un ensamblado satélite correspondiente a una referencia cultural específica. Para controlar el proceso de reserva, use el constructor <xref:System.Resources.NeutralResourcesLanguageAttribute.%23ctor%28System.String%2CSystem.Resources.UltimateResourceFallbackLocation%29> y proporcione un valor para el parámetro <xref:System.Resources.UltimateResourceFallbackLocation> que especifique si el Administrador de recursos debe extraer los recursos de reserva del ensamblado principal o de un ensamblado satélite.

En el ejemplo de .NET Framework siguiente se usa el atributo <xref:System.Resources.NeutralResourcesLanguageAttribute> para almacenar los recursos de reserva de una aplicación en un ensamblado satélite para el idioma francés (`fr`). El ejemplo tiene dos archivos de recursos basados en texto que definen un recurso de cadena única denominado `Greeting`. El primero, resources.fr.txt, contiene un recurso de idioma francés.

```text
Greeting=Bon jour!
```

El segundo, resources.ru.txt, contiene un recurso de idioma ruso.

```text
Greeting=Добрый день
```

Estos dos archivos se compilan en archivos .resources al ejecutar el [generador de archivos de recursos (Resgen.exe)](../tools/resgen-exe-resource-file-generator.md) desde la línea de comandos. Para el recurso de idioma francés, el comando es:

**resgen.exe resources.fr.txt**

Para el recurso de idioma ruso, el comando es:

**resgen.exe resources.ru.txt**

Los archivos .resources se insertan en bibliotecas de vínculos dinámicos mediante la ejecución de [Assembly Linker (Al.exe)](../tools/al-exe-assembly-linker.md) desde la línea de comandos para el recurso de idioma francés de la manera siguiente:

**al /t:lib /embed:resources.fr.resources /culture:fr /out:fr\Example1.resources.dll**

y para el recurso de idioma ruso de la manera siguiente:

**al /t:lib /embed:resources.ru.resources /culture:ru /out:ru\Example1.resources.dll**

El código fuente de la aplicación reside en un archivo denominado Example1.cs o Example1.vb. Incluye el atributo <xref:System.Resources.NeutralResourcesLanguageAttribute> para indicar que el recurso de aplicación predeterminado se encuentra en el subdirectorio fr. Crea una instancia del Administrador de recursos, recupera el valor del recurso `Greeting` y lo muestra en la consola.

[!code-csharp[Conceptual.Resources.Packaging#1](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.resources.packaging/cs/example1.cs#1)]
[!code-vb[Conceptual.Resources.Packaging#1](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.resources.packaging/vb/example1.vb#1)]

Después, puede compilar código fuente de C# desde la línea de comandos de la manera siguiente:

```console
csc Example1.cs
```

El comando para el compilador de Visual Basic es muy parecido:

```console
vbc Example1.vb
```

Dado que no hay ningún recurso insertado en el ensamblado principal, no es necesario compilar con el modificador `/resource`.

Cuando se ejecute el ejemplo desde un sistema cuyo idioma sea distinto del ruso, se mostrará la salida siguiente:

```output
Bon jour!
```

## <a name="suggested-packaging-alternative"></a>Alternativa de empaquetado sugerida

Las restricciones de tiempo o de presupuesto podrían impedir la creación de un conjunto de recursos para cada una de las referencias culturales secundarias que admite la aplicación. En su lugar, puede crear un único ensamblado satélite para la referencia cultural principal que todas las referencias culturales secundarias relacionadas puedan usar. Por ejemplo, puede proporcionar un único ensamblado satélite en inglés (en) para que lo recuperen los usuarios que soliciten recursos en inglés específicos de una región y un único ensamblado satélite en alemán (de) para los usuarios que soliciten recursos en alemán específicos de una región. Por ejemplo, las solicitudes de alemán de Alemania (de-DE), Austria (de-AT) y Suiza (de-CH) recurrirán al ensamblado satélite en alemán (de). Los recursos predeterminados constituyen la reserva final y, por tanto, deben ser los recursos que solicitará la mayoría de los usuarios de la aplicación, por lo que debe elegir cuidadosamente estos recursos. Este método implementa recursos menos específicos de la referencia cultural, pero puede reducir considerablemente los costos de localización de la aplicación.

## <a name="see-also"></a>Vea también

- [Recursos de aplicaciones de escritorio](index.md)
- [Caché global de ensamblados](../app-domains/gac.md)
- [Crear archivos de recursos](creating-resource-files-for-desktop-apps.md)
- [Crear ensamblados satélite](creating-satellite-assemblies-for-desktop-apps.md)
