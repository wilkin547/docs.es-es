---
title: "Cambios en tiempo de ejecuci&#243;n en .NET Framework 4.5.1 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "compatibilidad de aplicaciones"
  - "cambios en tiempo de ejecución"
  - ".NET Framework 4.5.1"
ms.assetid: da880ad7-ba0a-4368-b340-705e3533c351
caps.latest.revision: 15
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 15
---
# Cambios en tiempo de ejecuci&#243;n en .NET Framework 4.5.1
En raras ocasiones, los cambios en tiempo de ejecución pueden afectar a las aplicaciones existentes compiladas para [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] o 4.5 pero que se ejecutan en el runtime 4.51. Incluyen cambios en las áreas siguientes:  
  
-   [Core](#Core)  
  
-   [Windows Communication Foundation (WCF)](#WCF)  
  
 La columna de ámbito de las tablas siguientes especifica la importancia de cada cambio:  
  
-   Principal. Cambio significativo que afecta a un gran número de aplicaciones o que requiere una modificación sustancial del código. Observe que ninguno de los cambios en tiempo de ejecución pertenecen a esta categoría.  
  
-   Secundario. Cambio que afecta a un pequeño número de aplicaciones o que requiere ligeras modificaciones en el código.  
  
-   Avanzado. Cambio que afecta a aplicaciones de escenarios muy concretos que no son frecuentes.  
  
-   Transparente. Cambio que no tiene ningún efecto apreciable en el programador o el usuario de la aplicación. No es necesario modificar la aplicación debido a este cambio.  
  
<a name="Core"></a>   
## <a name="core-runtime-changes"></a>Cambios principales en el runtime  
  
|Característica|Cambio|Impacto|Ámbito|  
|-------------|------------|------------|-----------|  
|<xref:System.Collections.Concurrent.ConcurrentDictionary%602?displayProperty=fullName> serialización</TKey, TValue>|Un <xref:System.Collections.Concurrent.ConcurrentDictionary%602> objeto serializado en .NET Framework 4.5 con la <xref:System.Runtime.Serialization.NetDataContractSerializer> no se puede deserializar sólo debido a cambios internos en el tipo de .NET Framework 4.5.1 y 4.5.2.\</TKey, TValue><br /><br /> Este cambio *no* aplicar en los escenarios siguientes:<br /><br /> Un <xref:System.Collections.Concurrent.ConcurrentDictionary%602> objeto serializa en .NET Framework 4.5 y deserializar en el [!INCLUDE[net_v46](../../../includes/net-v46-md.md)].</TKey, TValue> El <xref:System.Runtime.Serialization.NetDataContractSerializer> en el [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] puede deserializar el objeto.<br /><br /> Un <xref:System.Collections.Concurrent.ConcurrentDictionary%602> objeto se serializa en una versión posterior de .NET Framework y se deserializan en .NET Framework 4.5.\</TKey, TValue> El <xref:System.Runtime.Serialization.NetDataContractSerializer> en .NET Framework 4.5 es capaz de deserializar el objeto.<br /><br /> Versión de la serialización y deserialización de un <xref:System.Collections.Concurrent.ConcurrentDictionary%602> objeto entre cualquier versión de .NET Framework después de .NET Framework 4.5.</TKey, TValue> Este cambio se aplica a los objetos serializados con .NET Framework 4.5 *sólo*.|Dos soluciones están disponibles si es necesario serializar un <xref:System.Collections.Concurrent.ConcurrentDictionary%602> objeto de .NET Framework 4.5 y deserializarla en una versión posterior de .NET Framework:\</TKey, TValue><br /><br /> Utilizar un serializador alternativo, como el <xref:System.Runtime.Serialization.DataContractSerializer> o <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>.<br /><br /> Actualización a la [!INCLUDE[net_v46](../../../includes/net-v46-md.md)], que admite la deserialización de <xref:System.Collections.Concurrent.ConcurrentDictionary%602> objeto serializado con .NET Framework 4.5.\</TKey, TValue>|Secundaria|  
|<xref:System.Diagnostics.Tracing.EventListener?displayProperty=fullName> (clase)|<xref:System.Diagnostics.Tracing.EventListener> trunca las cadenas con valores null incrustados. Caracteres null no son compatibles con el <xref:System.Diagnostics.Tracing.EventSource> clase.|El cambio sólo afecta a las aplicaciones que utilizan <xref:System.Diagnostics.Tracing.EventListener> leer <xref:System.Diagnostics.Tracing.EventSource> datos en proceso y que utilizan caracteres null como delimitadores.|Borde|  
|<xref:System.Diagnostics.Tracing.EventSource?displayProperty=fullName> (clase)|El runtime ahora aplica el contrato que especifica lo siguiente: una clase derivada de <xref:System.Diagnostics.Tracing.EventSource> que define un ETW de método de evento debe llamar a la clase base <xref:System.Diagnostics.Tracing.EventSource.WriteEvent%2A?displayProperty=fullName> método con el identificador de evento seguido por los mismos argumentos que se pasaron al método de evento ETW.|Un <xref:System.IndexOutOfRangeException> excepción se produce si un <xref:System.Diagnostics.Tracing.EventListener> lee <xref:System.Diagnostics.Tracing.EventSource> datos en proceso para un origen de eventos que infringe este contrato.<br /><br /> Consulte [mitigación: método EventSource.WriteEvent](../../../docs/framework/migration-guide/mitigation-eventsource-writeevent-method-calls.md)|Secundaria|  
|Deserialización de objetos a través de dominios de aplicación|En algunos casos, cuando una aplicación usa dos o más dominios de aplicación con distintas bases de aplicación, un intento de deserializar objetos en el contexto de llamada lógico entre dominios de aplicación produce una excepción.|Este problema se produce en un escenario muy específico. Para obtener más información y la mitigación, vea [mitigación: deserialización de objetos a través de dominios de aplicación](../../../docs/framework/migration-guide/mitigation-deserialization-of-objects-across-app-domains.md).|Borde|  
|<xref:System.IO.Stream.Dispose%2A?displayProperty=fullName> (método)|En [!INCLUDE[win8_appstore_long](../../../includes/win8-appstore-long-md.md)] aplicaciones, [!INCLUDE[wrt](../../../includes/wrt-md.md)] adaptadores de secuencia ya no llaman el <xref:System.IO.Stream.FlushAsync%2A> método desde el <xref:System.IO.Stream.Dispose%2A> método.|Este cambio debe ser transparente. Los desarrolladores pueden restaurar el comportamiento anterior escribiendo código similar al siguiente:<br /><br /> `using (System.IO.Stream stream = GetWindowsRuntimeStream() As Stream)  {     // do something     await stream.FlushAsync();   }`|Transparente|  
  
<a name="WCF"></a>   
## <a name="windows-communication-foundation-wcf-runtime-changes"></a>Cambios en tiempo de ejecución de Windows Communication Foundation (WCF)  
  
|Característica|Cambio|Impacto|Ámbito|  
|-------------|------------|------------|-----------|  
|[Valor](http://msdn.microsoft.com/library/ms731336.aspx) de configuración|Este valor establece la memoria mínima que debe estar disponible en el servidor para que se pueda activar un servicio WCF. Está diseñado para evitar <xref:System.OutOfMemoryException> excepciones. En [!INCLUDE[net_v45](../../../includes/net-v45-md.md)], este valor no tiene ningún efecto. En [!INCLUDE[net_v451](../../../includes/net-v451-md.md)], se respeta este valor.|Se produce una excepción si la memoria libre disponible en el servidor web es menor que el porcentaje definido por la opción de configuración. Algunos servicios WCF que se iniciaban y ejecutaban correctamente en un entorno de memoria restringida ahora pueden producir errores.<br /><br /> Consulte [mitigación: configuración minFreeMemoryPercentageToActiveService](../../../docs/framework/migration-guide/mitigation-minfreememorypercentagetoactiveservice-configuration-setting.md).|Secundaria|  
  
## <a name="see-also"></a>Vea también  
 [Cambios de redestinación](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-5-1.md)   
 [Compatibilidad de aplicaciones en 4.5](../../../docs/framework/migration-guide/application-compatibility-in-the-net-framework-4-5.md)   
 [Compatibilidad de aplicaciones en 4.5.2](../../../docs/framework/migration-guide/application-compatibility-in-the-net-framework-4-5-2.md)