---
title: Leer o escribir la clase XAMLServices y XAML básico
ms.date: 03/30/2017
helpviewer_keywords:
- XAML [XAML Services], XamlServices class
- XamlServices class [XAML Services], how to use
ms.assetid: 6ac27fad-3687-4d7a-add1-3e90675fdfde
ms.openlocfilehash: 264a8c4abcf9a7efceb7c7accd786495d35476e5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "81433095"
---
# <a name="xamlservices-class-and-basic-xaml-reading-or-writing"></a>Clase XAMLServices y lectura o escritura XAML básica

<xref:System.Xaml.XamlServices>es una clase proporcionada por .NET que se puede usar para abordar escenarios XAML que no requieren acceso específico al flujo de nodo XAML o a la información del sistema de tipos XAML obtenida de esos nodos. <xref:System.Xaml.XamlServices>La API se puede resumir `Load` `Parse` de la siguiente manera: o para admitir una ruta de acceso de carga XAML, `Save` para admitir una ruta de acceso de guardado XAML y `Transform` para proporcionar una técnica que combina una ruta de acceso de carga y una ruta de acceso de guardado. `Transform` permite cambiar entre esquemas XAML distintos. Este tema resume las distintas clasificaciones de API y describe las diferencias existentes entre las sobrecargas de método específicas.

## <a name="load"></a>Cargar

Son varias las sobrecargas de <xref:System.Xaml.XamlServices.Load%2A> que implementan la lógica completa para una ruta de acceso de carga. Esta ruta usa XAML en ciertos formularios y genera un flujo de nodo XAML. La mayoría de estas rutas de acceso de carga usan XAML en un formulario de archivo de texto XML codificado. No obstante, también puede cargar un flujo general o un origen XAML cargado previamente que ya esté incluido en otra implementación de <xref:System.Xaml.XamlReader> .

La sobrecarga más simple en la mayoría de los escenarios es <xref:System.Xaml.XamlServices.Load%28System.String%29>. Esta sobrecarga tiene un parámetro `fileName` que consiste simplemente en el nombre de un archivo de texto que contiene el XAML que se debe cargar. Resulta adecuada para escenarios de aplicación como los correspondientes a aplicaciones de plena confianza, que han serializado con anterioridad el estado o los datos en el equipo local. También resulta útil en marcos donde se define el modelo de aplicación y se desea cargar uno de los archivos estándar que establecen el comportamiento de la aplicación, la interfaz de usuario de inicio u otras capacidades definidas por el marco en las que se usa XAML.

Los escenarios de<xref:System.Xaml.XamlServices.Load%28System.IO.Stream%29> son similares. Esta sobrecarga puede resultar útil cuando es el usuario quien elige los archivos que se deben cargar, porque <xref:System.IO.Stream> es una salida frecuente de otras API de <xref:System.IO> , que pueden acceder a un sistema de archivos. O bien, podría acceder a los orígenes XAML a través de descargas asincrónicas u otras técnicas de red que también proporcionan un flujo (la carga desde un flujo o un origen seleccionado por el usuario puede conllevar implicaciones de seguridad. Para obtener más información, vea [XAML Security Considerations](security-considerations.md)).

<xref:System.Xaml.XamlServices.Load%28System.IO.TextReader%29>y <xref:System.Xaml.XamlServices.Load%28System.Xml.XmlReader%29> son sobrecargas que dependen de lectores de formatos de versiones anteriores de .NET. Para usar estas sobrecargas, ya debería haber `Create` creado una instancia de lector y usar su API para cargar el XAML en el formulario correspondiente (texto o XML). No es relevante si previamente ha movido los punteros de registro en los otros lectores o ha realizado con ellos otras operaciones. La lógica de la ruta de acceso de carga de <xref:System.Xaml.XamlServices.Load%2A> siempre procesa la entrada XAML completa desde la raíz. Los escenarios siguientes podrían justificar el uso de estas sobrecargas:

- Superficies de diseño a las que se proporciona la capacidad de edición de XAML simple desde un editor de texto específico de XML existente.

- Variantes de los principales escenarios de <xref:System.IO> , donde se usan lectores dedicados para abrir archivos o flujos. La lógica procesa o comprueba el contenido de forma rudimentaria antes de intentar cargarlo como XAML.

Puede cargar un archivo o una secuencia, <xref:System.Xml.XmlReader> <xref:System.IO.TextReader>o <xref:System.Xaml.XamlReader> puede cargar un archivo , , o que ajusta la entrada XAML cargando con las API del lector.

Internamente, cada una de las sobrecargas anteriores se convierte en última instancia en <xref:System.Xaml.XamlServices.Load%28System.Xml.XmlReader%29>y, con el valor <xref:System.Xml.XmlReader> anterior, se crea un valor <xref:System.Xaml.XamlXmlReader>nuevo.

La firma de `Load` que se proporciona para los escenarios más avanzados es <xref:System.Xaml.XamlServices.Load%28System.Xaml.XamlReader%29>. Puede usarla en los casos siguientes:

- Ha definido su propia implementación de un <xref:System.Xaml.XamlReader>archivo .

- Si debe especificar una configuración de <xref:System.Xaml.XamlReader> distinta de la predeterminada.

Ejemplos de configuraciones no predeterminadas:

<xref:System.Xaml.XamlReaderSettings.AllowProtectedMembersOnRoot%2A>\
<xref:System.Xaml.XamlReaderSettings.BaseUri%2A>\
<xref:System.Xaml.XamlReaderSettings.IgnoreUidsOnPropertyElements%2A>\
<xref:System.Xaml.XamlReaderSettings.LocalAssembly%2A>\
<xref:System.Xaml.XamlReaderSettings.ValuesMustBeString%2A>.

El lector predeterminado para <xref:System.Xaml.XamlServices> es <xref:System.Xaml.XamlXmlReader>. Si proporciona la <xref:System.Xaml.XamlXmlReader> suya propia con la configuración, <xref:System.Xaml.XamlXmlReaderSettings>las siguientes son propiedades para establecer no predeterminadas:

<xref:System.Xaml.XamlXmlReaderSettings.CloseInput%2A>\
<xref:System.Xaml.XamlXmlReaderSettings.SkipXmlCompatibilityProcessing%2A>\
<xref:System.Xaml.XamlXmlReaderSettings.XmlLang%2A>\
<xref:System.Xaml.XamlXmlReaderSettings.XmlSpacePreserve%2A>

## <a name="parse"></a>Analizar

<xref:System.Xaml.XamlServices.Parse%2A> es como `Load` en el sentido de que también es una API de ruta de acceso de carga, que crea un flujo de nodo XAML desde la entrada XAML. Sin embargo, en este caso, la entrada XAML se proporciona directamente como una cadena que incluye todo el contenido XAML que se debe cargar. <xref:System.Xaml.XamlServices.Parse%2A> ofrece un enfoque más ligero y apropiado para los escenarios de aplicación que los escenarios de marco. Para obtener más información, vea <xref:System.Xaml.XamlServices.Parse%2A>. <xref:System.Xaml.XamlServices.Parse%2A>es sólo una <xref:System.Xaml.XamlServices.Load%28System.Xml.XmlReader%29> llamada envuelta <xref:System.IO.StringReader> que implica un internamente.

## <a name="save"></a>Save

Varias sobrecargas <xref:System.Xaml.XamlServices.Save%2A> de implementar la ruta de acceso de guardado. Todos los métodos <xref:System.Xaml.XamlServices.Save%2A> toman un gráfico de objetos como entrada y generan el resultado como un flujo, un archivo o una instancia de <xref:System.Xml.XmlWriter>/<xref:System.IO.TextWriter> .

Se espera que el objeto de entrada sea el objeto raíz de alguna representación de objeto. Podría tratarse de la raíz única de un objeto de negocios, de la raíz de un árbol de objetos de una página en un escenario de interfaz de usuario, de la superficie de edición de trabajo de una herramienta de diseño, o de otros conceptos de objeto raíz adecuados para los distintos escenarios.

En muchos escenarios, el árbol de objetos que guarda está <xref:System.Xaml.XamlServices.Load%2A> relacionado con una operación original que cargó XAML con o con otra API implementada por un marco de trabajo o un modelo de aplicación. En el árbol de objetos se pueden capturar diferencias debidas a cambios de estado, cambios donde la aplicación haya capturado la configuración en tiempo de ejecución de un usuario, cambios de XAML si la aplicación es una superficie de diseño XAML, etc. Con o sin cambios, el concepto de primera carga de XAML a partir del marcado para, a continuación, guardar de nuevo y comparar los dos formularios de marcado XAML, también se conoce como representación de ida y vuelta de XAML.

El desafío a la hora de guardar y serializar un objeto complejo que se establece en un formulario de marcado es lograr un equilibrio entre la representación completa, sin pérdida de información, y el nivel de detalle por el que el XAML suena menos natural. Además, los diferentes clientes de XAML pueden tener distintas definiciones o expectativas sobre cómo establecer dicho equilibrio. Las API de <xref:System.Xaml.XamlServices.Save%2A> representan una definición de este equilibrio. Las API de <xref:System.Xaml.XamlServices.Save%2A> usan el contexto de esquema XAML disponible y las características predeterminadas basadas en CLR de <xref:System.Xaml.XamlType>, <xref:System.Xaml.XamlMember>y otros conceptos del sistema de tipos XAML e intrínsecos de XAML, para determinar dónde se pueden optimizar determinadas construcciones de flujo de nodo XAML cuando se guardan de nuevo en el marcado. Por ejemplo, <xref:System.Xaml.XamlServices> guarda las rutas de acceso que pueden usar el contexto de esquema XAML predeterminado basado en CLR para resolver <xref:System.Xaml.XamlType> para los objetos, puede determinar <xref:System.Xaml.XamlType.ContentProperty%2A?displayProperty=nameWithType>y, a continuación, puede omitir las etiquetas de elemento de propiedad cuando escriben la propiedad en el contenido XAML del objeto.

<a name="transform"></a>
## <a name="transform"></a>Transformación

Para convertir o transformar XAML,<xref:System.Xaml.XamlServices.Transform%2A> vincula una ruta de acceso de carga y otra de guardado como una única operación. Puede usarse un contexto de esquema o un sistema de tipos de respaldo diferentes para <xref:System.Xaml.XamlReader> y <xref:System.Xaml.XamlWriter>, lo que afectará a cómo se transforma el XAML resultante. Esto funciona bien para las operaciones de transformaciones amplias.

Por lo general, <xref:System.Xaml.XamlServices.Transform%2A>no se usa en las operaciones en las que se examina cada uno de los nodos de un flujo de nodo XAML. En su lugar, deberá definir su propia serie de operaciones de ruta de acceso de carga y guardado, e interponer su propia lógica. En una de las rutas de acceso, use un par lector XAML-escritor XAML en torno a su propio bucle de nodo. Por ejemplo, cargue el XAML inicial con <xref:System.Xaml.XamlXmlReader> y recorra los nodos con llamadas de <xref:System.Xaml.XamlXmlReader.Read%2A> sucesivas. Desde el nivel de flujo de nodo XAML ya puede ajustar los nodos individuales (tipos, miembros, etc.) para aplicar una transformación, o dejar el nodo tal cual. A continuación, envíe el nodo hacia adelante hasta la API de `Write` correspondiente de un elemento <xref:System.Xaml.XamlObjectWriter> y escriba el objeto. Para obtener más información, consulta [Understanding XAML Node Stream Structures and Concepts](understanding-xaml-node-stream-structures-and-concepts.md).

## <a name="see-also"></a>Consulte también

- <xref:System.Xaml.XamlObjectWriter>
- <xref:System.Xaml.XamlServices>
- [Servicios XAML](../../../api/index.md)
