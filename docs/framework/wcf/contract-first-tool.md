---
description: 'Más información acerca de: herramienta de Contract-First'
title: Herramienta de contrato primero
ms.date: 03/30/2017
ms.assetid: 0a880690-f460-4475-a5f4-9f91ce08fcc6
ms.openlocfilehash: 6455fa866afd440e70062f8433356b13fe163a8c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99736406"
---
# <a name="contract-first-tool"></a>Herramienta de contrato primero

Los contratos de servicio deben crearse a menudo desde servicios existentes. En .NET Framework 4,5 y versiones posteriores, las clases de contrato de datos se pueden crear automáticamente a partir de servicios existentes mediante la herramienta contrato primero. Para usar la herramienta de contrato primero, el archivo de definición de esquema XML (XSD) se debe descargar localmente; la herramienta no puede importar contratos de datos remotos a través de HTTP.

 La herramienta contrato primero se integra en Visual Studio 2012 como una tarea de compilación. Los archivos de código generados por la tarea de compilación se crean cada vez que se compila el proyecto, de modo que el proyecto pueda adoptar fácilmente los cambios en el contrato de servicio subyacente.

 Entre los tipos de esquema que la herramienta de contrato primero puede importar se incluyen los siguientes:

```xml
<xsd:complexType>
 <xsd:simpleType>
 </xsd:simpleType>
</xsd:complexType>
```

 No se generarán tipos simples si son primitivos como `Int16` o `String`; no se generarán tipos complejos si son de tipo `Collection`. Los tipos tampoco se generarán si forman parte de otro `xsd:complexType`. En todos estos casos, se hará referencia a tipos existentes en el proyecto.

## <a name="adding-a-data-contract-to-a-project"></a>Agregar un contrato de datos a un proyecto

 Antes de poder usar la herramienta de contrato primero, el contrato de servicio (XSD) se debe agregar al proyecto. En esta información general, se usará el contrato siguiente para mostrar las funciones de contrato primero. Esta definición de servicio es un pequeño subconjunto del contrato de servicio usado por la API de búsqueda de Bing.

```xml
<?xml version="1.0" encoding="utf-8"?>
<xs:schema id="ServiceSchema"
    targetNamespace="http://tempuri.org/ServiceSchema.xsd"
    elementFormDefault="qualified"
    xmlns="http://tempuri.org/ServiceSchema.xsd"
    xmlns:mstns="http://tempuri.org/ServiceSchema.xsd"
    xmlns:xs="http://www.w3.org/2001/XMLSchema"
>
  <xs:complexType name="SearchRequest">
    <xs:sequence>
      <xs:element minOccurs="0" maxOccurs="1" name="Version" type="xs:string" default="2.2" />
      <xs:element minOccurs="0" maxOccurs="1" name="Market" type="xs:string" />
      <xs:element minOccurs="0" maxOccurs="1" name="UILanguage" type="xs:string" />
      <xs:element minOccurs="1" maxOccurs="1" name="Query" type="xs:string" />
      <xs:element minOccurs="1" maxOccurs="1" name="AppId" type="xs:string" />
      <xs:element minOccurs="0" maxOccurs="1" name="Latitude" type="xs:double" />
      <xs:element minOccurs="0" maxOccurs="1" name="Longitude" type="xs:double" />
      <xs:element minOccurs="0" maxOccurs="1" name="Radius" type="xs:double" />
    </xs:sequence>
  </xs:complexType>
  <xs:simpleType name="WebSearchOption">
    <xs:restriction base="xs:string">
      <xs:enumeration value="DisableHostCollapsing" />
      <xs:enumeration value="DisableQueryAlterations" />
    </xs:restriction>
  </xs:simpleType>
</xs:schema>
```

 Para agregar el contrato de servicio anterior al proyecto, haga clic con el botón derecho en el proyecto y seleccione **Agregar nuevo.**... Seleccione Definición de esquema en el panel WCF del cuadro de diálogo Plantillas y asigne al nuevo archivo el nombre SampleContract.xsd. Copie y pegue el código anterior en la vista de código del nuevo archivo.

## <a name="configuring-contract-first-options"></a>Configurar opciones de contrato primero

 Las opciones de contrato primero se pueden configurar en el menú propiedades de un proyecto WCF. Para habilitar el desarrollo de contrato primero, active la casilla **Habilitar xsd como lenguaje de definición de tipos** en la página WCF de la ventana Propiedades del proyecto.

 ![Captura de pantalla de las opciones de WCF con el desarrollo de contrato primero habilitado.](./media/contract-first-tool/contract-first-options.png)

 Para configurar propiedades avanzadas, haga clic en el botón Avanzadas.

 ![Cuadro de diálogo Configuración de generación de código de contrato avanzado.](./media/contract-first-tool/advanced-contract-settings.png)

 Se pueden configurar las opciones avanzadas siguientes para la generación de código desde contratos. Los valores solo se pueden configurar para todos los archivos del proyecto; no se pueden configurar para archivos individuales en este momento.

- **Modo de serializador**: este valor determina qué serializador se utiliza para leer archivos de contrato de servicio. Cuando se selecciona **serializador XML** , se deshabilitan las opciones **tipos de colección** y **reutilizar tipos** . Estas opciones solo se aplican al **serializador del contrato de datos**.

- **Tipos de reutilización**: este valor especifica qué bibliotecas se usan para la reutilización de tipos. Esta configuración solo se aplica si el **modo de serializador** se establece en **serializador de contrato de datos**.

- **Tipo de colección**: este valor especifica el tipo completo o calificado con el ensamblado que se va a usar para el tipo de datos de la colección. Esta configuración solo se aplica si el **modo de serializador** se establece en **serializador de contrato de datos**.

- **Tipo de diccionario**: este valor especifica el tipo completo o calificado con el ensamblado que se va a usar para el tipo de datos del diccionario.

- **EnableDataBinding**: este valor especifica si se debe implementar la <xref:System.ComponentModel.INotifyPropertyChanged> interfaz en todos los tipos de datos para implementar el enlace de datos.

- **ExcludedTypes**: este valor especifica la lista de tipos completos o calificados con el ensamblado que se van a excluir de los ensamblados a los que se hace referencia. Esta configuración solo se aplica si el **modo de serializador** se establece en **serializador de contrato de datos**.

- **GenerateInternalTypes**: este valor especifica si se van a generar clases marcadas como internas. Esta configuración solo se aplica si el **modo de serializador** se establece en **serializador de contrato de datos**.

- **GenerateSerializableTypes**: este valor especifica si se deben generar clases con el <xref:System.SerializableAttribute> atributo. Esta configuración solo se aplica si el **modo de serializador** se establece en **serializador de contrato de datos**.

- **ImportXMLTypes**: este valor especifica si se debe configurar el serializador de contrato de datos para aplicar el <xref:System.SerializableAttribute> atributo a las clases sin el <xref:System.Runtime.Serialization.DataContractAttribute> atributo.  Esta configuración solo se aplica si el **modo de serializador** se establece en **serializador de contrato de datos**.

- **SupportFx35TypedDataSets**: este valor especifica si se debe proporcionar funcionalidad adicional para los conjuntos de datos con tipo creados para .NET Framework 3,5. Cuando el  **modo de serializador** se establece en **serializador XML**, la <xref:System.Data.Design.TypedDataSetSchemaImporterExtensionFx35> extensión se agrega al importador de esquemas XML cuando este valor se establece en true. Cuando el  **modo de serializador** se establece en **serializador de contrato de datos**, el tipo se <xref:System.DateTimeOffset> excluirá de las referencias cuando este valor se establezca en false, de modo que <xref:System.DateTimeOffset> siempre se genere para versiones anteriores de .NET Framework.

- **InputXsdFiles**: esta configuración especifica la lista de archivos de entrada. Cada archivo debe contener un esquema XML válido.

- **Idioma**: este valor especifica el idioma del código de contrato generado. El valor debe ser reconocible por <xref:System.CodeDom.Compiler.CodeDomProvider>.

- **NamespaceMappings**: esta configuración especifica las asignaciones de los espacios de nombres de destino XSD a los espacios de nombres CLR. Cada asignación debe usar el formato siguiente:

    ```xml
    "Schema Namespace, CLR Namespace"
    ```

     El serializador XML solo acepta una asignación en el formato siguiente:

    ```xml
    "*, CLR Namespace"
    ```

- **OutputDirectory**: este valor especifica el directorio donde se generarán los archivos de código.

 Los valores se usarán para generar tipos de contrato de servicio a partir de los archivos de contrato de servicio cuando se compile el proyecto.

## <a name="using-contract-first-development"></a>Mediante desarrollo de contrato primero

 Después de agregar el contrato de servicio al proyecto y confirmar la configuración de compilación, compile el proyecto presionando **F6**. Los tipos definidos en el contrato de servicio estarán disponibles para su uso en el proyecto.

 Para usar los tipos definidos en el contrato de servicio, agregue una referencia a `ContractTypes` en el espacio de nombres actual:

```csharp
using MyProjectNamespace.ContractTypes;
```

 Los tipos definidos en el contrato de servicio se podrán resolver en el proyecto, como se muestra a continuación:

 ![Clase SearchRequest que se muestra en IntelliSense después de escribir las primeras letras.](./media/contract-first-tool/service-contract-types.png)

 Los tipos generados por la herramienta se crean en el archivo GeneratedXSDTypes.cs. De forma predeterminada, el archivo se crea en el \<project directory> \<build configuration> directorio/obj//XSDGeneratedCode/ El esquema de ejemplo al principio de este artículo se convierte de la manera siguiente:

```csharp
//------------------------------------------------------------------------------
// <auto-generated>
//     This code was generated by a tool.
//     Runtime Version:4.0.30319.17330
//
//     Changes to this file may cause incorrect behavior and will be lost if
//     the code is regenerated.
// </auto-generated>
//------------------------------------------------------------------------------

namespace TestXSD3.ContractTypes
{
    using System.Xml.Serialization;

    /// <remarks/>
    [System.CodeDom.Compiler.GeneratedCodeAttribute("System.Xml", "4.0.30319.17330")]
    [System.SerializableAttribute()]
    [System.Diagnostics.DebuggerStepThroughAttribute()]
    [System.ComponentModel.DesignerCategoryAttribute("code")]
    [System.Xml.Serialization.XmlTypeAttribute(Namespace="http://tempuri.org/ServiceSchema.xsd")]
    [System.Xml.Serialization.XmlRootAttribute(Namespace="http://tempuri.org/ServiceSchema.xsd", IsNullable=true)]
    public partial class SearchRequest
    {

        private string versionField;

        private string marketField;

        private string uILanguageField;

        private string queryField;

        private string appIdField;

        private double latitudeField;

        private bool latitudeFieldSpecified;

        private double longitudeField;

        private bool longitudeFieldSpecified;

        private double radiusField;

        private bool radiusFieldSpecified;

        public SearchRequest()
        {
            this.versionField = "2.2";
        }

        /// <remarks/>
        [System.ComponentModel.DefaultValueAttribute("2.2")]
        public string Version
        {
            get
            {
                return this.versionField;
            }
            set
            {
                this.versionField = value;
            }
        }

        /// <remarks/>
        public string Market
        {
            get
            {
                return this.marketField;
            }
            set
            {
                this.marketField = value;
            }
        }

        /// <remarks/>
        public string UILanguage
        {
            get
            {
                return this.uILanguageField;
            }
            set
            {
                this.uILanguageField = value;
            }
        }

        /// <remarks/>
        public string Query
        {
            get
            {
                return this.queryField;
            }
            set
            {
                this.queryField = value;
            }
        }

        /// <remarks/>
        public string AppId
        {
            get
            {
                return this.appIdField;
            }
            set
            {
                this.appIdField = value;
            }
        }

        /// <remarks/>
        public double Latitude
        {
            get
            {
                return this.latitudeField;
            }
            set
            {
                this.latitudeField = value;
            }
        }

        /// <remarks/>
        [System.Xml.Serialization.XmlIgnoreAttribute()]
        public bool LatitudeSpecified
        {
            get
            {
                return this.latitudeFieldSpecified;
            }
            set
            {
                this.latitudeFieldSpecified = value;
            }
        }

        /// <remarks/>
        public double Longitude
        {
            get
            {
                return this.longitudeField;
            }
            set
            {
                this.longitudeField = value;
            }
        }

        /// <remarks/>
        [System.Xml.Serialization.XmlIgnoreAttribute()]
        public bool LongitudeSpecified
        {
            get
            {
                return this.longitudeFieldSpecified;
            }
            set
            {
                this.longitudeFieldSpecified = value;
            }
        }

        /// <remarks/>
        public double Radius
        {
            get
            {
                return this.radiusField;
            }
            set
            {
                this.radiusField = value;
            }
        }

        /// <remarks/>
        [System.Xml.Serialization.XmlIgnoreAttribute()]
        public bool RadiusSpecified
        {
            get
            {
                return this.radiusFieldSpecified;
            }
            set
            {
                this.radiusFieldSpecified = value;
            }
        }
    }

    /// <remarks/>
    [System.CodeDom.Compiler.GeneratedCodeAttribute("System.Xml", "4.0.30319.17330")]
    [System.SerializableAttribute()]
    [System.Xml.Serialization.XmlTypeAttribute(Namespace="http://tempuri.org/ServiceSchema.xsd")]
    [System.Xml.Serialization.XmlRootAttribute(Namespace="http://tempuri.org/ServiceSchema.xsd", IsNullable=false)]
    public enum WebSearchOption
    {

        /// <remarks/>
        DisableHostCollapsing,

        /// <remarks/>
        DisableQueryAlterations,
    }
}
```

## <a name="errors-and-warnings"></a>Errores y advertencias

 Los errores y advertencias detectados al analizar el esquema XSD aparecerán como errores de compilación y advertencias.

## <a name="interface-inheritance"></a>Herencia de interfaz

 No es posible usar la herencia de interfaz con el desarrollo de contrato primero; esto es coherente con el modo en el que las interfaces interactúan en otras operaciones. Para usar una interfaz que herede una interfaz base, use dos puntos de conexión independientes. El primer punto de conexión usa el contrato heredado y el segundo implementa la interfaz base.
