---
title: Espacios de nombres y asignación de espacios de nombres XAML para WPF
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- custom classes [WPF], mapping namespaces to
- XAML [WPF], namespaces
- namespace mapping [WPF]
- assemblies [WPF], mapping namespaces to
- mapping namespaces [WPF]
- XAML [WPF], namespace mapping
- classes [WPF], mapping namespaces to
- namespaces [WPF]
ms.assetid: 5c0854e3-7470-435d-9fe2-93eec9d3634e
ms.openlocfilehash: 9e93d3cd417d0d075fcebb8327ec51799884f8d6
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/16/2018
ms.locfileid: "45664649"
---
# <a name="xaml-namespaces-and-namespace-mapping-for-wpf-xaml"></a>Espacios de nombres y asignación de espacios de nombres XAML para WPF
En este tema se explica con mayor detalle la presencia y el propósito de las dos asignaciones de espacio de nombres XAML que se encuentran a menudo en la etiqueta raíz de cada archivo XAML de WPF. También se describe cómo generar asignaciones similares para usar elementos definidos en su propio código y/o dentro de ensamblados independientes.  
  
  
## <a name="what-is-a-xaml-namespace"></a>¿Qué es un espacio de nombres XAML?  
 Un espacio de nombres XAML es, realmente, una extensión del concepto de espacio de nombres XML. Las técnicas para especificar un espacio de nombres XAML se basan en la sintaxis del espacio de nombres XML, la convención de usar los URI como identificadores de los espacio de nombres y el uso de prefijos para proporcionar un medio para hacer referencia a varios espacios de nombres del mismo origen de marcado, entre otros. El concepto principal que se agrega a la definición XAML del espacio de nombres XML es que un espacio de nombres XAML implica un ámbito de singularidad para los usos de marcado y también influye en cómo las entidades de marcado están respaldadas potencialmente por espacios de nombres CLR y ensamblados concretos a los que se hace referencia. El concepto de un contexto de esquema XAML influye también en esta última consideración. Pero para el propósito de cómo trabaja WPF con espacios de nombres XAML, puede pensar en los espacios de nombres XAML como en un espacio de nombres XAML predeterminado, el espacio de nombres del lenguaje XAML, y cualquier otro espacio de nombres XAML según lo asigna directamente el marcado XAML para respaldar espacios de nombres CLR y ensamblados específicos a los que se hace referencia.  
  
<a name="The_WPF_and_XAML_Namespace_Declarations"></a>   
## <a name="the-wpf-and-xaml-namespace-declarations"></a>Declaraciones de espacios de nombres en XAML y WPF  
 Dentro de las declaraciones de espacios de nombres de la etiqueta raíz de muchos archivos XAML, observará que normalmente hay dos declaraciones de espacio de nombres XML. La primera declaración asigna el espacio de nombres cliente WPF / marco XAML global como predeterminado:  
  
 `xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"`  
  
 La segunda declaración asigna un espacio de nombres XAML independiente (normalmente) al prefijo `x:`.  
  
 `xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"`  
  
 La relación entre estas declaraciones es que la asignación del prefijo `x:` admite los elementos intrínsecos que forman parte de la definición del lenguaje XAML, y [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] es una implementación que usa XAML como lenguaje y define un vocabulario de sus objetos para XAML. Dado que los usos del vocabulario de WPF van a ser mucho más comunes que los usos de los elementos intrínsecos de XAML, el vocabulario de WPF se asigna como valor predeterminado.  
  
 La convención del prefijo `x:` para asignar los elementos intrínsecos del lenguaje XAML va seguida de las plantillas de proyecto, los ejemplos de código y la documentación de las características del lenguaje de este [!INCLUDE[TLA2#tla_sdk](../../../../includes/tla2sharptla-sdk-md.md)]. El espacio de nombres XAML define muchas de las características usadas normalmente que son necesarias incluso para las aplicaciones básicas de WPF. Por ejemplo, para combinar cualquier código subyacente con un archivo XAML a través de una clase parcial, debe denominar esa clase como el atributo `x:Class` del elemento raíz del archivo XAML pertinente. Por otra parte, cualquier elemento definido en una página XAML al que quiera obtener acceso como recurso con clave debe tener el atributo `x:Key` establecido en el elemento en cuestión. Para obtener más información sobre estos y otros aspectos de XAML, vea [Información general sobre XAML (WPF)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md) o [Detalles de la sintaxis XAML](../../../../docs/framework/wpf/advanced/xaml-syntax-in-detail.md).  
  
<a name="Mapping_To_Custom_Classes_and_Assemblies"></a>   
## <a name="mapping-to-custom-classes-and-assemblies"></a>Asignar a clases y ensamblados personalizados  
 Puede asignar espacios de nombres XML a ensamblados usando una serie de tokens dentro de una declaración de prefijo `xmlns`, de manera parecida al modo en que se asignan a prefijos los espacios de nombres XAML estándar de WPF y de los elementos intrínsecos de XAML.  
  
 La sintaxis acepta los siguientes tokens con nombre posibles y valores:  
  
 `clr-namespace:` El espacio de nombres CLR declarado dentro del ensamblado que contiene los tipos públicos que se exponen como elementos.  
  
 `assembly=` El ensamblado que contiene la totalidad o parte del espacio de nombres [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] al que se hace referencia. Este valor suele ser simplemente el nombre del ensamblado, no la ruta de acceso, y no incluye la extensión (como .dll o .exe). La ruta de acceso a ese ensamblado se debe establecer como referencia de proyecto en el archivo de proyecto que contiene el XAML que se va a asignar. Para incorporar el control de versiones y la firma de nombre seguro, el `assembly` valor puede ser una cadena definida por <xref:System.Reflection.AssemblyName>, en lugar del nombre de cadena simple.  
  
 Observe que el carácter que separa el token `clr-namespace` de su valor es un signo de dos puntos (:), mientras que el carácter que separa el token `assembly` de su valor es un signo igual (=). El carácter que se usa entre estos dos tokens es un punto y coma. Además, no incluya espacios en blanco en cualquier lugar en la declaración.  
  
### <a name="a-basic-custom-mapping-example"></a>Ejemplo de asignación personalizada básica  
 En el siguiente código se define un ejemplo de clase personalizada:  
  
```csharp  
namespace SDKSample {  
    public class ExampleClass : ContentControl {  
        public ExampleClass() {  
        ...  
        }  
    }  
}  
```  
  
```vb  
Namespace SDKSample  
    Public Class ExampleClass  
        Inherits ContentControl  
         ...  
        Public Sub New()  
        End Sub  
    End Class  
End Namespace  
```  
  
 A continuación, esta clase personalizada se compila en una biblioteca, que se denomina `SDKSampleLibrary` según la configuración del proyecto (no se muestra).  
  
 Para hacer referencia a esta clase personalizada, es necesario incluirla como referencia para su proyecto actual, lo que suele hacerse mediante la interfaz de usuario del Explorador de soluciones en Visual Studio.  
  
 Ahora que tiene una biblioteca que contiene una clase, y una referencia a ella en la configuración del proyecto, puede agregar la siguiente asignación de prefijo como parte del elemento raíz en XAML:  
  
 `xmlns:custom="clr-namespace:SDKSample;assembly=SDKSampleLibrary"`  
  
 Para combinarlo todo, el siguiente XAML incluye la asignación personalizada junto con las asignaciones predeterminadas y de x: en la etiqueta raíz. Después, usa una referencia con prefijo para crear una instancia de `ExampleClass` en esa interfaz de usuario:  
  
```xaml  
<Page x:Class="WPFApplication1.MainPage"  
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"   
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"  
    xmlns:custom="clr-namespace:SDKSample;assembly=SDKSampleLibrary">  
  ...  
  <custom:ExampleClass/>  
...  
</Page>  
```  
  
### <a name="mapping-to-current-assemblies"></a>Asignar a ensamblados actuales  
 Se puede omitir `assembly` si el `clr-namespace` al que se hace referencia se define dentro del mismo ensamblado que el código de aplicación que hace referencia a las clases personalizadas. Otra sintaxis equivalente para este caso consiste en especificar `assembly=`, sin ningún token de cadena tras el signo igual.  
  
 Las clases personalizadas no se pueden usar como elemento raíz de una página si se definen en el mismo ensamblado. No es necesario asignar las clases parciales; únicamente es necesario asignar las clases que no son la clase parcial de una página de la aplicación si piensa hacerles referencia como elementos en XAML.  
  
<a name="Mapping_CLR_Namespaces_to_XML_Namespaces_in_an"></a>   
## <a name="mapping-clr-namespaces-to-xml-namespaces-in-an-assembly"></a>Asignar espacios de nombres CLR a espacios de nombres XML en un ensamblado  
 WPF define un atributo CLR que usan los procesadores XAML para asignar varios espacios de nombres CLR a un mismo espacio de nombres XAML. Este atributo, <xref:System.Windows.Markup.XmlnsDefinitionAttribute>, se coloca en el nivel de ensamblado en el código fuente que genera el ensamblado. El código fuente del ensamblado WPF usa este atributo para asignar los distintos espacios de nombres comunes, como <xref:System.Windows> y <xref:System.Windows.Controls>, a la [!INCLUDE[TLA#tla_wpfxmlnsv1](../../../../includes/tlasharptla-wpfxmlnsv1-md.md)] espacio de nombres.  
  
 El <xref:System.Windows.Markup.XmlnsDefinitionAttribute> toma dos parámetros: el nombre de espacio de nombres XML/XAML y el nombre del espacio de nombres CLR. Más de un <xref:System.Windows.Markup.XmlnsDefinitionAttribute> puede existir para asignar varios espacios de nombres CLR al mismo espacio de nombres XML. Una vez asignados, si se quiere se puede hacer referencia también a los miembros de esos espacios de nombres aunque no estén completos, proporcionando la instrucción `using` adecuada en la página de código subyacente de la clase parcial. Para obtener más información, vea <xref:System.Windows.Markup.XmlnsDefinitionAttribute>.  
  
## <a name="designer-namespaces-and-other-prefixes-from-xaml-templates"></a>Espacios de nombres de diseñador y otros prefijos de las plantillas XAML  
 Si trabaja con entornos de desarrollo o herramientas de diseño para XAML de WPF, tal vez observe que hay otros espacios de nombres XAML / prefijos definidos dentro del marcado XAML.  
  
 [!INCLUDE[wpfdesigner_current_long](../../../../includes/wpfdesigner-current-long-md.md)] usa un espacio de nombres de diseñador que está asignado normalmente al prefijo `d:`. Las plantillas de proyecto de WPF más recientes podrían pre-asignar este espacio de nombres XAML para admitir el intercambio de XAML entre [!INCLUDE[wpfdesigner_current_long](../../../../includes/wpfdesigner-current-long-md.md)] y otros entornos de diseño. Este espacio de nombres XAML de diseño se usa para perpetuar el estado del diseño mientras la interfaz de usuario basada en XAML en el diseñador va y vuelve. También lo usan características como `d:IsDataSource`, que habilitan los orígenes de datos en tiempo de ejecución en un diseñador.  
  
 Otro prefijo que podría ver asignado es `mc:`. `mc:` es para ofrecer compatibilidad de marcado, y aprovecha un modelo de compatibilidad de marcado que no es necesariamente específico de XAML. Hasta cierto punto, las características de compatibilidad de marcado se pueden usar para intercambiar XAML entre marcos o entre otros límites de implementación de respaldo, trabajar entre contextos de esquema XAML, ofrecer compatibilidad para modos limitados en los diseñadores, etc. Para obtener más información sobre los conceptos de compatibilidad de marcado y su relación con WPF, vea [Características del lenguaje de compatibilidad de marcado (mc:)](../../../../docs/framework/wpf/advanced/markup-compatibility-mc-language-features.md).  
  
## <a name="wpf-and-assembly-loading"></a>WPF y carga de ensamblados  
 El contexto de esquema XAML para WPF se integra con el modelo de aplicación de WPF, que a su vez usa el concepto definido por el CLR de <xref:System.AppDomain>. La secuencia siguiente describe cómo el contexto de esquema XAML interpreta cómo cargar ensamblados o buscar tipos en tiempo de ejecución o en tiempo de diseño, según el uso WPF de <xref:System.AppDomain> y otros factores.  
  
1.  Recorrer en iteración el <xref:System.AppDomain>, busca un ensamblado ya cargado que coincida con todos los aspectos del nombre, empezando desde el último ensamblado cargado.  
  
2.  Si el nombre está calificado, llame a <xref:System.Reflection.Assembly.Load%28System.String%29?displayProperty=nameWithType> en el nombre completo.  
  
3.  Si el nombre corto + el token de clave pública de un nombre completo coinciden con el ensamblado desde el que se ha cargado el marcado, devuelva dicho ensamblado.  
  
4.  Usar el nombre corto + el token de clave pública para llamar a <xref:System.Reflection.Assembly.Load%28System.String%29?displayProperty=nameWithType>.  
  
5.  Si el nombre es incompleto, llame a <xref:System.Reflection.Assembly.LoadWithPartialName%2A?displayProperty=nameWithType>.  
  
 El XAML dinámico no usa el Paso 3; no hay ensamblado desde el que cargar.  
  
 XAML compilado para WPF (generado mediante XamlBuildTask) no utiliza los ensamblados ya cargados desde <xref:System.AppDomain> (paso 1). Además, el nombre nunca debe estar incompleto en la salida de XamlBuildTask, por lo que el Paso 5 no se aplica.  
  
 El BAML compilado (generado mediante PresentationBuildTask) usa todos los pasos, aunque el BAML tampoco debe contener nombres de ensamblado incompletos.  
  
## <a name="see-also"></a>Vea también  
 [Descripción de los espacios de nombres XML](https://go.microsoft.com/fwlink/?LinkId=98069)  
 [Información general sobre XAML (WPF)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)
