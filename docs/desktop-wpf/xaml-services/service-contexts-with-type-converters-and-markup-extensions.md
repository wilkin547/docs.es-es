---
title: Contextos de servicio disponibles para los convertidores de tipos y las extensiones de marcado
ms.date: 03/30/2017
helpviewer_keywords:
- XAML [XAML Services], type converter services how-to
ms.assetid: b4dad00f-03da-4579-a4e9-d8d72d2ccbce
ms.openlocfilehash: 59c4385eb4df8c622be6164cdb0a1a911c445ca8
ms.sourcegitcommit: c2d9718996402993cf31541f11e95531bc68bad0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/27/2020
ms.locfileid: "81432897"
---
# <a name="service-contexts-available-to-type-converters-and-markup-extensions"></a>Contextos de servicio disponibles para los convertidores de tipos y las extensiones de marcado
Los autores de los tipos que admiten los usos de la extensión de marcado y el convertidor de tipos deben tener a menudo la información contextual sobre dónde se encuentra un uso en el marcado o en la estructura gráfica del objeto adyacente. Puede ser necesaria cierta información para que se cree una instancia correcta del objeto proporcionado o para que puedan crearse referencias a objetos existentes del gráfico del objeto. Cuando se usa los servicios XAML de .NET, el contexto que podría ser necesario se expone como una serie de interfaces de servicio. El código de soporte de la extensión de marcado o el convertidor de tipos puede consultar un servicio usando un contexto de proveedor de servicio que esté disponible y se haya pasado desde <xref:System.Xaml.XamlObjectWriter> o tipos relacionados. El contexto de esquema XAML está disponible directamente con uno de estos servicios. En este tema se describe cómo acceder a los contextos de servicio desde una implementación de convertidor de valor y se enumeran los servicios normalmente disponibles y sus funciones.

## <a name="obtaining-services"></a>Obtener servicios

Como implementador de un convertidor de valores, suele necesitar acceder a algún tipo de contexto en el que se aplica el convertidor de valores. Este contexto puede incluir información como el contexto de esquema XAML activo, acceso al sistema de asignación de tipos que proporcionan el contexto de esquema XAML y el escritor de objetos XAML, etc. Los servicios disponibles para una implementación de convertidor de tipos o extensión de marcado se comunican con los parámetros de contexto que forman parte de la firma de cada método virtual. En todos los casos, <xref:System.IServiceProvider> debe estar implementado en el contexto y puede llamar a <xref:System.IServiceProvider.GetService%2A?displayProperty=nameWithType> para pedir un servicio.

## <a name="services-for-a-markup-extension"></a>Servicios para una extensión de marcado

<xref:System.Windows.Markup.MarkupExtension> solo tiene un método virtual, <xref:System.Windows.Markup.MarkupExtension.ProvideValue%2A>. El parámetro de entrada `serviceProvider` indica cómo se comunican los servicios a las implementaciones cuando un procesador XAML llama a la extensión de marcado. En el siguiente pseudocódigo se muestra cómo una implementación de extensión de marcado puede consultar los servicios en su <xref:System.Windows.Markup.MarkupExtension.ProvideValue%2A>:

```csharp
public override object ProvideValue(IServiceProvider serviceProvider)
{
...
    // Get the IXamlTypeResolver from the service provider
    if (serviceProvider == null)
    {
        throw new ArgumentNullException("serviceProvider");
    }
    IXamlTypeResolver xamlTypeResolver = serviceProvider.GetService(typeof(IXamlTypeResolver)) as IXamlTypeResolver;
    if (xamlTypeResolver == null)
   {
        throw new ArgumentException("IXamlTypeResolver"));
    }
...
}
```

## <a name="services-for-a-type-converter"></a>Servicios para un convertidor de tipos

<xref:System.ComponentModel.TypeConverter> tiene cuatro métodos virtuales que usan un contexto de servicio y que admiten usos XAML. Cada uno de estos métodos pasa un parámetro de entrada `context` . Este parámetro es de tipo <xref:System.ComponentModel.ITypeDescriptorContext>, pero esa interfaz hereda <xref:System.IServiceProvider>; por lo tanto, hay un método <xref:System.IServiceProvider.GetService%2A> disponible para implementaciones de convertidor de tipos.

En el siguiente pseudocódigo se muestra cómo una implementación de convertidor de tipos para usos XAML puede consultar los servicios de una de sus invalidaciones, en este caso <xref:System.ComponentModel.TypeConverter.ConvertFrom%2A>:

```csharp
public override object ConvertFrom(ITypeDescriptorContext typeDescriptorContext,
  CultureInfo cultureInfo,
  object source)
{
    IRootObjectProvider rootProvider = typeDescriptorContext.GetService(typeof(IRootObjectProvider)) as IRootObjectProvider;
    if (rootProvider != null && source is String)
    {
        //return something, else ...
    }
    throw GetConvertFromException(source);
}
```

## <a name="services-for-a-value-serializer"></a>Servicios para un serializador de valor

Para el contexto de serializador de valor, se usa un tipo de proveedor de servicios que es específico de la clase <xref:System.Windows.Markup.ValueSerializer> , <xref:System.Windows.Markup.IValueSerializerContext>. Ese contexto se pasa a las invalidaciones de los cuatro métodos virtuales <xref:System.Windows.Markup.ValueSerializer> . Llame a <xref:System.IServiceProvider.GetService%2A> desde el contexto para obtener servicios.

## <a name="using-the-xaml-service-provider-contexts"></a>Uso de los contextos de proveedor de servicio XAML

El proveedor <xref:System.IServiceProvider.GetService%2A> de servicios para el acceso a los servicios XAML disponibles para las extensiones de marcado o convertidores de tipos se implementa como una clase interna, con la exposición solo a través de la interfaz y cómo se pasa al contexto relevante. Cada vez que una operación de procesamiento XAML en las implementaciones predeterminadas de servicios XAML de .NET de ruta de acceso de carga o ruta de acceso de guardado invoca la extensión de marcado relevante o métodos de convertidor de tipos que requieren un contexto de servicio, se pasa este objeto interno. Dependiendo de las circunstancias, el contexto de servicio del sistema proporciona `MarkupExtensionContext` o `TextSyntaxContext`, pero las características específicas de ambas clases son internas. La interacción con estas clases se limita a pedir servicios desde ellas con <xref:System.IServiceProvider.GetService%2A>.

## <a name="available-services-from-the-net-xaml-service-context"></a>Servicios disponibles desde el contexto de servicio XAML de .NET

Servicios XAML de .NET define servicios para extensiones de marcado, convertidores de tipos, serializadores de valores y potencialmente otros usos. En las secciones siguientes se describe cada uno de estos servicios y se proporcionan instrucciones sobre cómo usarlos en una implementación.

### <a name="iserviceprovider"></a>IServiceProvider

**Documentación de referencia**:<xref:System.IServiceProvider>

**Relevante para:** Operación básica de una infraestructura basada en servicios <xref:System.IServiceProvider.GetService%2A?displayProperty=nameWithType>en .NET para que pueda llamar a .

### <a name="itypedescriptorcontext"></a>ITypeDescriptorContext

**Documentación de referencia**:<xref:System.ComponentModel.ITypeDescriptorContext>

Deriva de <xref:System.IServiceProvider>. Esta clase representa el contexto de las firmas estándares <xref:System.ComponentModel.TypeConverter> ; <xref:System.ComponentModel.TypeConverter> es una clase que existe desde .NET Framework 1.0. Es anterior a XAML y el escenario XAML <xref:System.ComponentModel.TypeConverter> para la conversión de tipo de valor de cadena. En el contexto de servicios <xref:System.ComponentModel.TypeConverter> XAML de .NET, los métodos de se implementan explícitamente. El comportamiento de la implementación explícita indica a los llamadores que la API <xref:System.ComponentModel.ITypeDescriptorContext> no es relevante para los sistemas de tipos XAML ni para leer o escribir objetos desde XAML. <xref:System.ComponentModel.ITypeDescriptorContext.Container%2A>, <xref:System.ComponentModel.ITypeDescriptorContext.Instance%2A>, <xref:System.ComponentModel.ITypeDescriptorContext.PropertyDescriptor%2A> y, `null` por lo general, devolver desde contextos de servicios XAML de .NET.

### <a name="ivalueserializercontext"></a>IValueSerializerContext

**Documentación de referencia**:<xref:System.Windows.Markup.IValueSerializerContext>

Se deriva de <xref:System.ComponentModel.ITypeDescriptorContext> y también se basa en las implementaciones explícitas para suprimir las implicaciones falsas sobre el sistema de tipos XAML. Admite los métodos del asistente de búsqueda estática en <xref:System.Windows.Markup.ValueSerializer>.

### <a name="ixamltyperesolver"></a>IXamlTypeResolver

**Documentación de referencia**:<xref:System.Windows.Markup.IXamlTypeResolver>

**Definida por:**  <xref:System.Windows.Markup> espacio de nombres, ensamblado System.Xaml

**Relevante para:** escenarios de ruta de acceso de carga y la interacción con el contexto de esquema XAML

**API de servicio:**  <xref:System.Windows.Markup.IXamlTypeResolver.Resolve%2A>

Puede influir en la asignación de tipo XAML a CLR que es necesaria cuando el escritor de XAML construye un objeto CLR en un gráfico de objetos. <xref:System.Windows.Markup.IXamlTypeResolver.Resolve%2A> procesa una cadena potencialmente calificada con prefijo que corresponde a un nombre de tipo XAML (<xref:System.Xaml.XamlType.Name%2A?displayProperty=nameWithType>) y devuelve un CLR <xref:System.Type>. La resolución de los tipos depende normalmente y en gran medida del contexto de esquema XAML. Solo el contexto de esquema XAML conoce consideraciones como qué ensamblados se cargan y a cuáles de estos ensamblados se puede o se debe acceder para la resolución de tipo.

### <a name="iuricontext"></a>IUriContext

**Documentación de referencia**:<xref:System.Windows.Markup.IUriContext>

**Definida por:**  <xref:System.Windows.Markup> espacio de nombres, ensamblado System.Xaml

**Relevante para:** tratar rutas de acceso de carga y guardado de valores de miembro que son URI o valores `x:Uri` .

**API de servicio:**  <xref:System.Windows.Markup.IUriContext.BaseUri%2A>

Este servicio notifica una raíz URI disponible globalmente, si existe. La raíz URI puede usarse para resolver los URI relativos como URI absolutos o viceversa. Este escenario es principalmente relevante para los servicios de aplicación expuestos por un marco determinado o para las capacidades de una clase de elemento raíz usada con frecuencia en un marco. El URI base se puede establecer como una opción de lector XAML que se pasa a la escritura de objeto XAML y es notificada por este servicio.

### <a name="iambientprovider"></a>IAmbientProvider

**Documentación de referencia**:<xref:System.Xaml.IAmbientProvider>

**Definida por:**  <xref:System.Xaml> espacio de nombres, ensamblado System.Xaml

**Relevante para:** el tratamiento de rutas de acceso de carga y aplazamientos de búsquedas de control u optimizaciones.

**API de servicio:**  <xref:System.Xaml.IAmbientProvider.GetAllAmbientValues%2A>, otras tres.

El concepto de ambiente en XAML es una técnica para marcar a un miembro determinado de un tipo como ambiente. Como alternativa, un tipo puede ser ambiente para que todos los valores de propiedad que contienen una instancia del tipo se consideren propiedades de ambiente. Las extensiones de marcado o los convertidores de tipos que son más adelante el flujo de nodo XAML y que son descendientes del gráfico de objetos pueden acceder a la propiedad de ambiente o instancia de tipo en tiempo de carga; o bien, puede usar el conocimiento de la estructura de ambiente en el momento de guardar. Esto puede afectar al grado de calificación que se necesita para resolver tipos para otros servicios, como <xref:System.Windows.Markup.IXamlTypeResolver> o `x:Type`. Consulte también <xref:System.Xaml.AmbientPropertyValue>.

### <a name="ixamlschemacontextprovider"></a>IXamlSchemaContextProvider

**Documentación de referencia**:<xref:System.Xaml.IXamlSchemaContextProvider>

**Definida por:**  <xref:System.Xaml> espacio de nombres, ensamblado System.Xaml

**Relevante para:** ruta de acceso de carga y cualquier operación que deba resolver un tipo XAML como un tipo de copia de seguridad.

**API de servicio:**  <xref:System.Xaml.IXamlSchemaContextProvider.SchemaContext%2A>

El contexto de esquema XAML es necesario para las operaciones de carga diferidas porque el mismo contexto del esquema debe actuar sobre el área diferida para integrar el contenido diferido. Para más información sobre la función del contexto de esquema XAML, vea [XAML Services](../../../api/index.md).

### <a name="irootobjectprovider"></a>IRootObjectProvider

**Documentación de referencia**:<xref:System.Xaml.IRootObjectProvider>

**Definida por:**  <xref:System.Xaml> espacio de nombres, ensamblado System.Xaml

**Relevante para:** ruta de acceso de carga.

**API de servicio:**  <xref:System.Xaml.IRootObjectProvider.RootObject%2A>

Este escenario es relevante para los servicios de aplicación expuestos por un marco determinado o por las capacidades de una clase de elemento raíz usada con frecuencia en un marco. Un escenario para obtener el objeto raíz es la conexión con el código subyacente y la conexión de eventos. Por ejemplo, la implementación de WPF de `x:Class` se usa para compilar el marcado y conectar cualquier atributo de controlador de eventos que se encuentra en cualquier otra posición del marcado XAML. El punto de conexión de las clases parciales definidas por el código subyacente y el marcado para la compilación del marcado está en el elemento raíz.

### <a name="ixamlnamespaceresolver"></a>IXamlNamespaceResolver

**Documentación de referencia**:<xref:System.Xaml.IXamlNamespaceResolver>

**Definida por:**  <xref:System.Xaml> espacio de nombres, ensamblado System.Xaml

**Relevante para:** la ruta de acceso de carga y la ruta de acceso de guardado.

**API de servicio:** <xref:System.Xaml.IXamlNamespaceResolver.GetNamespace%2A> para la ruta de acceso de carga y <xref:System.Xaml.IXamlNamespaceResolver.GetNamespacePrefixes%2A> para la ruta de acceso de almacenamiento.

<xref:System.Xaml.IXamlNamespaceResolver> es un servicio que puede devolver un URI/identificador de espacio de nombres XAML basado en su prefijo según se ha asignado en el marcado XAML original.

### <a name="iprovidevaluetarget"></a>IProvideValueTarget

**Documentación de referencia**:<xref:System.Windows.Markup.IProvideValueTarget>

**Definida por:**  <xref:System.Windows.Markup> espacio de nombres, ensamblado System.Xaml

**Relevante para:** la ruta de acceso de carga y la ruta de acceso de guardado.h.

**API de servicio:**<xref:System.Windows.Markup.IProvideValueTarget.TargetObject%2A>, . <xref:System.Windows.Markup.IProvideValueTarget.TargetProperty%2A>  

<xref:System.Windows.Markup.IProvideValueTarget> permite que una extensión de marcado o tipo de convertidor obtenga el contexto sobre dónde está actuando en tiempo de carga. Las implementaciones pueden usar este contexto para invalidar un uso. Por ejemplo, WPF tiene lógica dentro de algunas de sus extensiones de marcado como <xref:System.Windows.DynamicResourceExtension>. Las lógica comprueba <xref:System.Windows.Markup.IProvideValueTarget.TargetProperty%2A> para asegurarse de que la extensión solo se use para establecer las propiedades de dependencia (o una lista breve de otras propiedades de no dependencia).

### <a name="ixamlnameresolver"></a>IXamlNameResolver

**Documentación de referencia**:<xref:System.Xaml.IXamlNameResolver>

**Definida por:**  <xref:System.Xaml> espacio de nombres, ensamblado System.Xaml

**Relevante para:** Cargar la definición del gráfico `x:Name`de `x:Reference`objetos de ruta de acceso, resolver objetos identificados por , , o técnicas específicas del marco de trabajo.

**API de servicio:**  <xref:System.Xaml.IXamlNameResolver.Resolve%2A>; otras API para los escenarios más avanzados como el tratamiento de las referencias adelantadas.

La implementación del `x:Reference` control de los servicios XAML de .NET se basa en este servicio. Los marcos o las herramientas específicos que admiten el marco usan este servicio para el control de `x:Name` o el control de propiedades (<xref:System.Windows.Markup.RuntimeNamePropertyAttribute> con atributos) equivalente.

### <a name="idestinationtypeprovider"></a>IDestinationTypeProvider

**Documentación de referencia**:<xref:System.Xaml.IDestinationTypeProvider>

**Definida por:**  <xref:System.Xaml> espacio de nombres, ensamblado System.Xaml

**Relevante para:** la resolución de la ruta de acceso de carga de la información de tipo CLR indirecta.

**API de servicio:** <xref:System.Xaml.IDestinationTypeProvider.GetDestinationType%2A>

Para obtener más información, vea <xref:System.Xaml.IDestinationTypeProvider>.

## <a name="see-also"></a>Consulte también

- <xref:System.Windows.Markup.MarkupExtension>
- <xref:System.Xaml.XamlObjectWriter>
- [Información general sobre las extensiones de marcado para el lenguaje XAML](markup-extensions-overview.md)
- [Información general sobre los convertidores de tipos para XAML](type-converters-overview.md)
