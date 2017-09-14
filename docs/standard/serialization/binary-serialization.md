---
title: "Serialización binaria"
ms.date: 08/11/2017
ms.prod: .net
ms.topic: article
helpviewer_keywords:
- binary serialization
- serialization, about serialization
- deserialization
- binary serialization, about serialization
- binary serialization, .net core serialization
- serialization, cross-framework
ms.assetid: 2b1ea3be-1152-4032-b2b3-07794054c405
caps.latest.revision: 5
author: ViktorHofer
ms.author: mairaw
ms.translationtype: HT
ms.sourcegitcommit: 717bcb6f9f72a728d77e2847096ea558a9c50902
ms.openlocfilehash: 995430b2426cb124ee889ed49cc7260c68138151
ms.contentlocale: es-es
ms.lasthandoff: 08/21/2017

---
# <a name="binary-serialization"></a>Serialización binaria

La serialización se puede definir como el proceso de almacenar el estado de un objeto a los medios de almacenamiento. Durante este proceso, los campos públicos y privados del objeto y el nombre de la clase, incluso el ensamblado que contiene la clase, se convierten en una secuencia de bytes, que se escribe a continuación en un flujo de datos. Cuando se deserializa el objeto como consecuencia, se crea un clon exacto del objeto original.

Al implementar un mecanismo de la serialización en un entorno orientado a objetos, tiene que realizar varios intercambios entre la facilidad de uso y la flexibilidad. El proceso se puede automatizar en gran medida, con tal de que sea proporcionado el control suficiente sobre el proceso. Por ejemplo, las situaciones se pueden presentar donde la serialización binaria simple no es suficiente, o podría haber una razón concreta para decidir qué campos en una clase necesitan ser serializados. Las secciones siguientes examinan el sólido mecanismo de serialización proporcionado con .NET y resaltan varias características importantes que permiten personalizar el proceso para satisfacer las necesidades.

> [!NOTE]
> El estado de un objeto UTF-8 o UTF-7 codificado no se conserva si el objeto se serializa y se deserializa utilizando distintas versiones de .NET Framework.

[!INCLUDE [binary-serialization-warning](../../../includes/binary-serialization-warning.md)]

Al igual que la naturaleza de la serialización binaria permite la modificación de los miembros privados de un objeto y, por tanto, cambiar el estado del mismo, se recomiendan otros marcos de trabajo de serialización como JSON.NET que operan en la superficie de la API pública.

## <a name="binary-serialization-in-net-core"></a>Serialización binaria en .NET Core

.NET Core es compatible con la serialización binaria con un subconjunto de tipos. Puede ver la lista de tipos compatibles en la sección [Tipos serializables](#serializable-types). Se garantiza que el conjunto definido de tipos es serializable entre .NET Framework 4.5.1 y versiones posteriores y .NET Core 2.0 y versiones posteriores. Otras implementaciones de .NET, como Mono, no son oficialmente compatibles, pero también deberían funcionar.

### <a name="serializable-types"></a>Tipos serializables

- <xref:System.AggregateException?displayProperty=fullName>   
- <xref:System.Array?displayProperty=fullName>   
- <xref:System.ArraySegment%601?displayProperty=fullName>   
- <xref:System.Attribute?displayProperty=fullName>   
- <xref:System.Boolean?displayProperty=fullName>   
- <xref:System.Byte?displayProperty=fullName>   
- <xref:System.Char?displayProperty=fullName>   
- <xref:System.Collections.ArrayList?displayProperty=fullName>   
- <xref:System.Collections.BitArray?displayProperty=fullName>   
- <xref:System.Collections.Comparer?displayProperty=fullName>   
- <xref:System.Collections.DictionaryEntry?displayProperty=fullName>   
- <xref:System.Collections.Generic.Comparer%601?displayProperty=fullName>   
- <xref:System.Collections.Generic.Dictionary%602?displayProperty=fullName>   
- <xref:System.Collections.Generic.EqualityComparer%601?displayProperty=fullName>   
- <xref:System.Collections.Generic.HashSet%601?displayProperty=fullName>   
- <xref:System.Collections.Generic.KeyValuePair%602?displayProperty=fullName>   
- <xref:System.Collections.Generic.LinkedList%601?displayProperty=fullName>   
- <xref:System.Collections.Generic.List%601?displayProperty=fullName>   
- <xref:System.Collections.Generic.Queue%601?displayProperty=fullName>   
- <xref:System.Collections.Generic.SortedDictionary%602?displayProperty=fullName>   
- <xref:System.Collections.Generic.SortedList%602?displayProperty=fullName>   
- <xref:System.Collections.Generic.SortedSet%601?displayProperty=fullName>   
- <xref:System.Collections.Generic.Stack%601?displayProperty=fullName>   
- <xref:System.Collections.Hashtable?displayProperty=fullName>   
- <xref:System.Collections.ObjectModel.Collection%601?displayProperty=fullName>   
- <xref:System.Collections.ObjectModel.KeyedCollection%602?displayProperty=fullName>   
- <xref:System.Collections.ObjectModel.ObservableCollection%601?displayProperty=fullName>   
- <xref:System.Collections.ObjectModel.ReadOnlyCollection%601?displayProperty=fullName>   
- <xref:System.Collections.ObjectModel.ReadOnlyDictionary%602?displayProperty=fullName>   
- <xref:System.Collections.ObjectModel.ReadOnlyObservableCollection%601?displayProperty=fullName>   
- <xref:System.Collections.Queue?displayProperty=fullName>   
- <xref:System.Collections.SortedList?displayProperty=fullName>   
- <xref:System.Collections.Specialized.HybridDictionary?displayProperty=fullName>   
- <xref:System.Collections.Specialized.ListDictionary?displayProperty=fullName>   
- <xref:System.Collections.Specialized.OrderedDictionary?displayProperty=fullName>   
- <xref:System.Collections.Specialized.StringCollection?displayProperty=fullName>   
- <xref:System.Collections.Specialized.StringDictionary?displayProperty=fullName>   
- <xref:System.Collections.Stack?displayProperty=fullName>   
- <xref:System.ComponentModel.BindingList%601?displayProperty=fullName>   
- <xref:System.Data.DataSet?displayProperty=fullName>   
- <xref:System.Data.DataTable?displayProperty=fullName>   
- <xref:System.Data.PropertyCollection?displayProperty=fullName>   
- <xref:System.Data.SqlTypes.SqlBoolean?displayProperty=fullName>   
- <xref:System.Data.SqlTypes.SqlByte?displayProperty=fullName>   
- <xref:System.Data.SqlTypes.SqlDateTime?displayProperty=fullName>   
- <xref:System.Data.SqlTypes.SqlDouble?displayProperty=fullName>   
- <xref:System.Data.SqlTypes.SqlGuid?displayProperty=fullName>   
- <xref:System.Data.SqlTypes.SqlInt16?displayProperty=fullName>   
- <xref:System.Data.SqlTypes.SqlInt32?displayProperty=fullName>   
- <xref:System.Data.SqlTypes.SqlInt64?displayProperty=fullName>   
- <xref:System.Data.SqlTypes.SqlString?displayProperty=fullName>   
- <xref:System.DateTime?displayProperty=fullName>   
- <xref:System.DateTimeOffset?displayProperty=fullName>   
- <xref:System.Decimal?displayProperty=fullName>   
- <xref:System.Double?displayProperty=fullName>   
- <xref:System.Drawing.Color?displayProperty=fullName>   
- <xref:System.Drawing.Point?displayProperty=fullName>   
- <xref:System.Drawing.PointF?displayProperty=fullName>   
- <xref:System.Drawing.Rectangle?displayProperty=fullName>   
- <xref:System.Drawing.RectangleF?displayProperty=fullName>   
- <xref:System.Drawing.Size?displayProperty=fullName>   
- <xref:System.Drawing.SizeF?displayProperty=fullName>   
- <xref:System.Enum?displayProperty=fullName>   
- <xref:System.Exception?displayProperty=fullName>   
- <xref:System.Globalization.CompareInfo?displayProperty=fullName>   
- <xref:System.Globalization.SortVersion?displayProperty=fullName>   
- <xref:System.Guid?displayProperty=fullName>   
- <xref:System.Int16?displayProperty=fullName>   
- <xref:System.Int32?displayProperty=fullName>   
- <xref:System.Int64?displayProperty=fullName>   
- <xref:System.IntPtr?displayProperty=fullName>   
- <xref:System.Net.Cookie?displayProperty=fullName>   
- <xref:System.Net.CookieCollection?displayProperty=fullName>   
- <xref:System.Net.CookieContainer?displayProperty=fullName>   
- <xref:System.Nullable%601?displayProperty=fullName>   
- <xref:System.Numerics.BigInteger?displayProperty=fullName>   
- <xref:System.Numerics.Complex?displayProperty=fullName>   
- <xref:System.Object?displayProperty=fullName>   
- <xref:System.SByte?displayProperty=fullName>   
- <xref:System.Single?displayProperty=fullName>   
- <xref:System.String?displayProperty=fullName>   
- <xref:System.StringComparer?displayProperty=fullName>   
- <xref:System.Text.StringBuilder?displayProperty=fullName>   
- <xref:System.TimeSpan?displayProperty=fullName>   
- <xref:System.TimeZoneInfo?displayProperty=fullName>   
- <xref:System.TimeZoneInfo.AdjustmentRule?displayProperty=fullName>   
- <xref:System.Tuple?displayProperty=fullName>   
- <xref:System.UInt16?displayProperty=fullName>   
- <xref:System.UInt32?displayProperty=fullName>   
- <xref:System.UInt64?displayProperty=fullName>   
- <xref:System.UIntPtr?displayProperty=fullName>   
- <xref:System.Uri?displayProperty=fullName>   
- <xref:System.ValueTuple?displayProperty=fullName>   
- <xref:System.ValueType?displayProperty=fullName>   
- <xref:System.Version?displayProperty=fullName>   
- <xref:System.WeakReference?displayProperty=fullName>   
- <xref:System.WeakReference%601?displayProperty=fullName>   

## <a name="in-this-section"></a>En esta sección

 [Conceptos de serialización](../../../docs/standard/serialization/serialization-concepts.md)  
 Describe dos escenarios en los que la serialización resulta útil: al almacenar datos persistentes y al pasar objetos a través de dominios de aplicaciones.  
  
 [Serialización básica](../../../docs/standard/serialization/basic-serialization.md)  
 Describe cómo utilizar los formateadores SOAP y binario para serializar los objetos.  
  
 [Serialización selectiva](../../../docs/standard/serialization/selective-serialization.md)  
 Describe cómo evitar que se serialicen algunos miembros de una clase.  
  
 [Serialización personalizada](../../../docs/standard/serialization/custom-serialization.md)  
 Describe cómo personalizar la serialización de una clase mediante la interfaz <xref:System.Runtime.Serialization.ISerializable>.  
  
 [Pasos del proceso de serialización](../../../docs/standard/serialization/steps-in-the-serialization-process.md)  
 Describe la medida que toma la serialización cuando se llama al método <xref:System.Runtime.Serialization.Formatter.Serialize%2A> en un formateador.  
  
 [Serialización tolerante a versiones](../../../docs/standard/serialization/version-tolerant-serialization.md)  
 Explica cómo crear tipos serializables que se pueden modificar con el tiempo sin hacer que las aplicaciones produzcan las excepciones.  
  
 [Directrices de serialización](../../../docs/standard/serialization/serialization-guidelines.md)  
 Proporciona algunas directrices general para decidir cuándo serializar un objeto.  
  
## <a name="reference"></a>Referencia  
 <xref:System.Runtime.Serialization>  
 Contiene clases que se pueden usar para serializar y deserializar objetos.  
  
## <a name="related-sections"></a>Secciones relacionadas  
 [Serialización SOAP y XML](../../../docs/standard/serialization/xml-and-soap-serialization.md)  
 Describe el mecanismo de la serialización XML que está incluido con Common Language Runtime.  
  
 [Seguridad y serialización](../../../docs/framework/misc/security-and-serialization.md)  
 Describe las instrucciones de la codificación seguras que hay que seguir al escribir el código que realiza la serialización.  
  
 [Objetos remotos](http://msdn.microsoft.com/en-us/515686e6-0a8d-42f7-8188-73abede57c58)  
 Describe los diversos métodos de comunicaciones disponibles en .NET Framework para las comunicaciones remotas.  
  
 [Servicios Web XML creados con ASP.NET y clientes de servicio Web XML](http://msdn.microsoft.com/en-us/1e64af78-d705-4384-b08d-591a45f4379c)  
 Proporciona los temas que describen y explican cómo programar los servicios Web XML creados utilizando ASP.NET.

