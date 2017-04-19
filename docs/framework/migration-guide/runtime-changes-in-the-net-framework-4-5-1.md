---
title: "Cambios en tiempo de ejecución en .NET Framework 4.5.1 | Microsoft Docs"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- application compatibility
- runtime changes
- .NET Framework 4.5.1
ms.assetid: da880ad7-ba0a-4368-b340-705e3533c351
caps.latest.revision: 15
author: rpetrusha
ms.author: ronpet
manager: wpickett
translationtype: Human Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 4e4903c2f25354005f95b3ed8f9728cfe8a0a92e
ms.lasthandoff: 04/18/2017

---
# <a name="runtime-changes-in-the-net-framework-451"></a>Cambios en tiempo de ejecución en .NET Framework 4.5.1
En raras ocasiones, los cambios en tiempo de ejecución pueden afectar a las aplicaciones existentes compiladas para [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] o 4.5 pero que se ejecutan en el runtime 4.51. Incluyen cambios en las áreas siguientes:  
  
-   [Principal](#Core)  
  
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
|<xref:System.Collections.Concurrent.ConcurrentDictionary%602?displayProperty=fullName> serialización|Un objeto <xref:System.Collections.Concurrent.ConcurrentDictionary%602> serializado en .NET Framework 4.5 con <xref:System.Runtime.Serialization.NetDataContractSerializer> no se puede deserializar en .NET Framework 4.5.1 y 4.5.2 solamente debido a cambios internos en el tipo.<br /><br /> Este cambio *no* se aplica a los siguientes escenarios:<br /><br /> Un objeto <xref:System.Collections.Concurrent.ConcurrentDictionary%602> serializado en .NET Framework 4.5 y deserializado en [!INCLUDE[net_v46](../../../includes/net-v46-md.md)]. <xref:System.Runtime.Serialization.NetDataContractSerializer> en [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] tiene la capacidad para deserializar el objeto.<br /><br /> Un objeto <xref:System.Collections.Concurrent.ConcurrentDictionary%602> serializado en una versión posterior de .NET Framework y deserializado en .NET Framework 4.5. <xref:System.Runtime.Serialization.NetDataContractSerializer> en .NET Framework 4.5 tiene la capacidad para deserializar el objeto.<br /><br /> La serialización y deserialización entre versiones de un objeto <xref:System.Collections.Concurrent.ConcurrentDictionary%602> entre cualquier versión de .NET Framework posterior a 4.5. Este cambio *solo* se aplica a los objetos serializados con .NET Framework 4.5.|Hay disponibles dos soluciones alternativas si es necesario serializar un objeto <xref:System.Collections.Concurrent.ConcurrentDictionary%602> en .NET Framework 4.5 y deserializarlo en una versión posterior de .NET Framework:<br /><br /> Use un serializador alternativo, como <xref:System.Runtime.Serialization.DataContractSerializer> o <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>.<br /><br /> Actualice a [!INCLUDE[net_v46](../../../includes/net-v46-md.md)], que admite la deserialización del objeto <xref:System.Collections.Concurrent.ConcurrentDictionary%602> serializado con .NET Framework 4.5.|Secundaria|  
|Clase <xref:System.Diagnostics.Tracing.EventListener?displayProperty=fullName>|<xref:System.Diagnostics.Tracing.EventListener> trunca las cadenas con valores nulos incrustados. La clase <xref:System.Diagnostics.Tracing.EventSource> no admite valores nulos.|El cambio solo afecta a las aplicaciones que usan <xref:System.Diagnostics.Tracing.EventListener> para leer datos <xref:System.Diagnostics.Tracing.EventSource> en proceso y usan caracteres nulos como delimitadores.|Borde|  
|Clase <xref:System.Diagnostics.Tracing.EventSource?displayProperty=fullName>|El runtime ahora aplica el contrato que especifica lo siguiente: una clase derivada de <xref:System.Diagnostics.Tracing.EventSource> que define un método de evento ETW debe llamar al método <xref:System.Diagnostics.Tracing.EventSource.WriteEvent%2A?displayProperty=fullName> de la clase base con el identificador de evento seguido de los mismos argumentos que se pasaron al método de evento ETW.|Se produce una excepción <xref:System.IndexOutOfRangeException> si <xref:System.Diagnostics.Tracing.EventListener> lee datos <xref:System.Diagnostics.Tracing.EventSource> en proceso para un origen del evento que incumple este contrato.<br /><br /> Consulte [Mitigación: Llamadas al método EventSource.WriteEvent](../../../docs/framework/migration-guide/mitigation-eventsource-writeevent-method-calls.md).|Secundaria|  
|Deserialización de objetos a través de dominios de aplicación|En algunos casos, cuando una aplicación usa dos o más dominios de aplicación con distintas bases de aplicación, un intento de deserializar objetos en el contexto de llamada lógico entre dominios de aplicación produce una excepción.|Este problema se produce en un escenario muy específico. Para obtener más información sobre la mitigación, vea [Mitigación: Deserialización de objetos en distintos dominios de aplicación](../../../docs/framework/migration-guide/mitigation-deserialization-of-objects-across-app-domains.md).|Borde|  
|Método <xref:System.IO.Stream.Dispose%2A?displayProperty=fullName>|En aplicaciones [!INCLUDE[win8_appstore_long](../../../includes/win8-appstore-long-md.md)], los adaptadores de secuencias [!INCLUDE[wrt](../../../includes/wrt-md.md)] ya no llaman al método <xref:System.IO.Stream.FlushAsync%2A> desde el método <xref:System.IO.Stream.Dispose%2A>.|Este cambio debe ser transparente. Los desarrolladores pueden restaurar el comportamiento anterior escribiendo código similar al siguiente:<br /><br /> `using (System.IO.Stream stream = GetWindowsRuntimeStream() As Stream)  {     // do something     await stream.FlushAsync();   }`|Transparente|  
  
<a name="WCF"></a>   
## <a name="windows-communication-foundation-wcf-runtime-changes"></a>Cambios en tiempo de ejecución de Windows Communication Foundation (WCF)  
  
|Característica|Cambio|Impacto|Ámbito|  
|-------------|------------|------------|-----------|  
|Valor de configuración [minFreeMemoryPercentageToActiveService](http://msdn.microsoft.com/library/ms731336.aspx)|Este valor establece la memoria mínima que debe estar disponible en el servidor para que se pueda activar un servicio WCF. Está diseñado para evitar excepciones <xref:System.OutOfMemoryException>. En [!INCLUDE[net_v45](../../../includes/net-v45-md.md)], este valor no tiene ningún efecto. En [!INCLUDE[net_v451](../../../includes/net-v451-md.md)], se respeta este valor.|Se produce una excepción si la memoria libre disponible en el servidor web es menor que el porcentaje definido por la opción de configuración. Algunos servicios WCF que se iniciaban y ejecutaban correctamente en un entorno de memoria restringida ahora pueden producir errores.<br /><br /> Consulte [Mitigación: Valor de configuración minFreeMemoryPercentageToActiveService](../../../docs/framework/migration-guide/mitigation-minfreememorypercentagetoactiveservice-configuration-setting.md).|Secundaria|  
  
## <a name="see-also"></a>Vea también  
 [Cambios de redestinación](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-5-1.md)   
 [Compatibilidad de aplicaciones en 4.5](../../../docs/framework/migration-guide/application-compatibility-in-the-net-framework-4-5.md)   
 [Compatibilidad de aplicaciones en 4.5.2](../../../docs/framework/migration-guide/application-compatibility-in-the-net-framework-4-5-2.md)
