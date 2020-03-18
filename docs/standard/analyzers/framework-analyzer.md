---
title: 'Analizadores de .NET Framework: .NET'
description: Obtenga información sobre cómo usar los analizadores de .NET Framework en el paquete de analizadores de .NET Framework para buscar y tratar los riesgos de seguridad
author: billwagner
ms.author: wiwagn
ms.date: 01/25/2018
ms.technology: dotnet-standard
ms.openlocfilehash: dd69671e709549fe0ad0f582e4d09b43f7321df2
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "78156002"
---
# <a name="the-net-framework-analyzer"></a>Analizador de .NET Framework

Puede usar el analizador de .NET Framework para buscar posibles problemas en el código de aplicación basado en .NET Framework. Este analizador busca posibles problemas y sugiere correcciones.

El analizador se ejecuta de forma interactiva en Visual Studio mientras escribe el código o como parte de una compilación de integración continua. Debe agregar el analizador al proyecto lo antes posible en el desarrollo. Cuanto antes encuentre los posibles problemas del código, más fácil será corregirlos. Aun así, puede agregarlo en cualquier momento del ciclo de desarrollo. Busca cualquier problema con el código existente y advierte sobre nuevos problemas mientras desarrolla.

## <a name="installing-and-configuring-the-net-framework-analyzer"></a>Instalar y configurar el analizador de .NET Framework

Los analizadores de .NET Framework deben instalarse como un paquete NuGet en todos los proyectos en los que quiera ejecutarlos. Solo los tiene que agregar un desarrollador al proyecto. El paquete de analizadores es una dependencia del proyecto y se ejecutará en el equipo de todos los desarrolladores cuando tengan la solución actualizada.

El analizador de .NET Framework se entrega en el paquete NuGet [Microsoft.NetFramework.Analyzers](https://www.nuget.org/packages/Microsoft.NetFramework.Analyzers/). Este paquete solo proporciona los analizadores específicos de .NET Framework, que incluye los analizadores de seguridad. En la mayoría de los casos, le interesará el paquete NuGet [Microsoft.CodeAnalysis.FxCopAnalyzers](https://www.nuget.org/packages/Microsoft.CodeAnalysis.FxCopAnalyzers).
El paquete de agregados FxCopAnalyzers contiene todos los analizadores de .NET Framework incluidos en el paquete Framework.Analyzers, así como los siguientes analizadores:

- [Microsoft.CodeQuality.Analyzers](https://www.nuget.org/packages/Microsoft.CodeQuality.Analyzers): proporciona instrucciones generales e instrucciones para las API de .NET Standard.
- [Microsoft.NetCore.Analyzers](https://www.nuget.org/packages/Microsoft.NetCore.Analyzers): proporciona analizadores específicos para las API de .NET Core.
- [Text.Analyzers](https://www.nuget.org/packages/Text.Analyzers): proporciona instrucciones para el texto incluido como código, incluidos los comentarios.

Para instalarlo, haga clic con el botón derecho en el proyecto y seleccione "Administrar dependencias".
En el explorador de NuGet, busque "NetFramework Analyzer" o, si lo prefiere, "Fx Cop Analyzer". Instale la versión estable más reciente en todos los proyectos de la solución.

## <a name="using-the-net-framework-analyzer"></a>Usar el analizador de .NET Framework

Una vez instalado el paquete NuGet, compile la solución. El analizador notificará los problemas que encuentre en el código base. Los problemas se notifican como advertencias en la ventana Lista de errores de Visual Studio, como se muestra en la siguiente imagen:

![problemas notificados por el analizador de marco](./media/framework-analyzers-2.png)

Al escribir el código, verá subrayados ondulados debajo de cualquier posible problema del código.
Mantenga el mouse sobre cualquier problema y verá detalles sobre este, además de sugerencias de cualquier posible corrección, como se muestra en la siguiente imagen:

![informe interactivo de los problemas encontrados por el analizador de .NET Framework](./media/framework-analyzers-1.png)

Los analizadores examinan el código en la solución y proporcionan una lista de advertencias de cualquiera de estos problemas:

### <a name="ca1058-types-should-not-extend-certain-base-types"></a>CA1058: Los tipos no deben ampliar ciertos tipos base

Hay un pequeño número de tipos en .NET Framework de los que no debe derivar directamente.

**Categoría:** diseño

**Gravedad:** advertencia

Información adicional: [CA1058: Los tipos no deben ampliar ciertos tipos base](/visualstudio/code-quality/ca1058-types-should-not-extend-certain-base-types)

### <a name="ca2153-do-not-catch-corrupted-state-exceptions"></a>CA2153: No capturar excepciones de estado dañado

Si se capturan excepciones de estado dañado, podrían enmascarar errores (por ejemplo, infracciones de acceso), lo que da como resultado un estado incoherente de la ejecución o lo que facilita a los atacantes poner en peligro un sistema. En su lugar, detecte y controle un conjunto más específico de tipos de excepción o vuelva a producir la excepción.

**Categoría:** seguridad

**Gravedad:** advertencia

Información adicional: [CA2153: No capturar excepciones de estado dañado](/visualstudio/code-quality/ca2153-avoid-handling-corrupted-state-exceptions)

### <a name="ca2229-implement-serialization-constructors"></a>CA2229: Implementar constructores de serialización

El analizador genera esta advertencia cuando crea un tipo que implementa la interfaz <xref:System.Runtime.Serialization.ISerializable> pero no define el constructor de serialización necesario. Para corregir una infracción de esta regla, implemente el constructor de serialización. Para una clase sellada, marque el constructor como privado; de lo contrario, márquelo como protegido. El constructor de serialización tiene la siguiente signatura:

```csharp
public class MyItemType
{
    // The special constructor is used to deserialize values.
    public MyItemType(SerializationInfo info, StreamingContext context)
    {
        // implementation removed.
    }
}
```

**Categoría:** uso

**Gravedad:** advertencia

Información adicional: [CA2229: Implementar constructores de serialización](/visualstudio/code-quality/ca2229-implement-serialization-constructors)

### <a name="ca2235-mark-all-non-serializable-fields"></a>CA2235: Marcar todos los campos no serializables

Un campo de instancia de un tipo que no es serializable se declara en un tipo que es serializable. Debe marcar explícitamente ese campo con el <xref:System.NonSerializedAttribute> para corregir esta advertencia.

**Categoría:** uso

**Gravedad:** advertencia

Información adicional: [CA2235: Marcar todos los campos no serializables](/visualstudio/code-quality/ca2235-mark-all-non-serializable-fields)

### <a name="ca2237-mark-iserializable-types-with-serializable"></a>CA2237: Marcar los tipos ISerializable con serializable

Para que Common Language Runtime reconozca los tipos como serializables, deben marcarse con el atributo <xref:System.SerializableAttribute> incluso si el tipo usa una rutina de serialización personalizada al implementar la interfaz <xref:System.Runtime.Serialization.ISerializable>.

**Categoría:** uso

**Gravedad:** advertencia

Información adicional: [CA2237: Marcar los tipos ISerializable con serializable](/visualstudio/code-quality/ca2237-mark-iserializable-types-with-serializableattribute)

### <a name="ca3075-insecure-dtd-processing-in-xml"></a>CA3075: Procesamiento de DTD no seguro en XML

Si usa instancias de <xref:System.Xml.XmlReaderSettings.DtdProcessing%2A> no seguras o hace referencia a orígenes de entidades externas, el analizador podría aceptar entradas que no sean de confianza y revelar información confidencial a atacantes.  

**Categoría:** seguridad

**Gravedad:** advertencia

Información adicional: [A3075: Procesamiento de DTD no seguro en XML](/visualstudio/code-quality/ca2237-mark-iserializable-types-with-serializableattribute)

### <a name="ca5350-do-not-use-weak-cryptographic-algorithms"></a>CA5350: No usar algoritmos criptográficos no seguros

Los algoritmos criptográficos se degradan con el paso del tiempo, ya que los ataques aumentan. En función del tipo y la aplicación de este algoritmo criptográfico, una mayor degradación de su intensidad de cifrado puede permitir a los atacantes leer mensajes cifrados, manipular mensajes cifrados, falsificar firmas digitales, manipular contenido con hash o poner en peligro los sistemas de cifrado basados en este algoritmo. Para el cifrado, use un algoritmo AES (AES-256, AES-192 y AES-128 son aceptables) con una longitud de clave mayor o igual que 128 bits. Para el hash, use una función hash de la familia SHA-2, como SHA-2 512, SHA-2 384 o SHA-2 256.

**Categoría:** seguridad

**Gravedad:** advertencia

Información adicional: [CA5350: No usar algoritmos criptográficos no seguros](/visualstudio/code-quality/ca5350-do-not-use-weak-cryptographic-algorithms)

### <a name="ca5351-do-not-use-broken-cryptographic-algorithms"></a>CA5351: No usar algoritmos criptográficos rotos

Existe un ataque que, a nivel computacional, puede interrumpir este algoritmo. De esta forma, los atacantes pueden interrumpir las garantías cifradas que debe proporcionar por diseño. En función del tipo y la aplicación de este algoritmo criptográfico, puede permitir a los atacantes leer mensajes cifrados, manipular mensajes cifrados, falsificar firmas digitales, manipular contenido con hash o poner en peligro los sistemas de cifrado basados en este algoritmo. Para el cifrado, use un algoritmo AES (AES-256, AES-192 y AES-128 son aceptables) con una longitud de clave mayor o igual que 128 bits. Para el hash, use una función hash de la familia SHA-2, como SHA512, SHA384 o SHA256. Para las firmas digitales, use RSA con una longitud de clave mayor o igual que 2048 bits, o ECDSA con una longitud de clave mayor o igual que 256 bits.

**Categoría:** seguridad

**Gravedad:** advertencia

Información adicional: [CA5351: No usar algoritmos criptográficos rotos](/visualstudio/code-quality/ca5351)
