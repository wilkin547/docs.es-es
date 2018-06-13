---
title: Seguimiento del diagnóstico
ms.date: 03/30/2017
ms.assetid: 28e77a63-d20d-4b6a-9caf-ddad86550427
ms.openlocfilehash: 56f79fb9140785188996cc413eca4dd530037ccd
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33363472"
---
# <a name="diagnostic-traces"></a>Seguimiento del diagnóstico
Los rastros son la publicación de mensajes concretos que se generan durante la ejecución de la aplicación. Cuando se utiliza traza debe existir un mecanismo para recopilar y registrar los mensajes que se envían. Los agentes de escucha son los objetos encargados de recibir los mensajes de seguimiento. Un agente de escucha se encarga de recopilar, almacenar y enrutar los mensajes de seguimiento. Los agentes de escucha dirigen los resultados del seguimiento a un destino apropiado, como un registro, una ventana o un archivo de texto.  
  
 Un tal agente de escucha, <xref:System.Diagnostics.DefaultTraceListener>, se crea y se inicializa automáticamente si la traza está habilitada. Si desea que los resultados de la traza se envíen a otros destinos adicionales, deberá crear e inicializar agentes de escucha adicionales. Los agentes de escucha que cree deben reflejar sus necesidades particulares. Por ejemplo, podría desear obtener un registro de texto con todo el resultado del seguimiento. En este caso, debe crear un agente de escucha que escriba en un nuevo archivo de texto cuando se habilite. Por otro lado, podría desear ver los resultados durante la aplicación de la ejecución. En ese caso, podría crear un agente de escucha que enviara todos los resultados a una ventana de consola. <xref:System.Diagnostics.EventLogTraceListener> puede enviar los resultados del seguimiento a un registro de eventos, y <xref:System.Diagnostics.TextWriterTraceListener> puede escribir esos mismos resultados en una secuencia  
  
## <a name="enabling-tracing"></a>Habilitar el seguimiento  
 Para habilitar los rastros durante el procesamiento de transacciones, debe modificar el archivo de configuración de su aplicación. A continuación se muestra un ejemplo.  
  
```xml  
<configuration>  
<system.diagnostics>  
     <sources>  
          <source name="System.Transactions" switchValue="Warning">  
               <listeners>  
                    <add name="tx"   
                     type="System.Diagnostics.XmlWriterTraceListener"   
                     initializeData= "tx.log" />  
               </listeners>  
          </source>  
     </sources>  
</system.diagnostics>  
</configuration>  
```  
  
 Los rastros <xref:System.Transactions> se escriben en el origen denominado "System.Transactions." Puede utilizar `add` para especificar el nombre y tipo de agente de escucha de seguimiento que desea utilizar. En nuestra configuración del ejemplo, denominamos "tx" del agente de escucha y agregamos el agente de escucha de seguimiento de .NET Framework estándar (<xref:System.Diagnostics.XmlWriterTraceListener>) como el tipo que deseamos utilizar. Utilice `initializeData` para establecer el nombre del archivo de registro para ese agente de escucha. Además, puede sustituir una ruta de acceso completa para un nombre de archivo simple.  
  
 A cada tipo de mensaje de seguimiento le está asignado un nivel para indicar su grado de importancia. Si el dominio de aplicación del nivel de seguimiento es igual o menor que el nivel de un tipo de evento, a continuación, se genera ese mensaje. `switchValue` controla el nivel de seguimiento en el archivo de configuración. Los niveles que están asociados a mensajes de seguimiento de diagnóstico se definen en la tabla siguiente.  
  
|Nivel de seguimiento|Descripción|  
|-----------------|-----------------|  
|Crítico|Los errores serios, como lo siguiente, han producido:<br /><br /> -Un error que puede provocar una pérdida de inmediata en funciones de usuario.<br />-Un evento que requiere que un administrador tomar medidas para evitar la pérdida de funcionalidad.<br />-Se bloquea el código.<br />: Este nivel de seguimiento también puede proporcionar suficiente contexto para interpretar otros seguimientos críticos. Esto puede ayudar a identificar la secuencia de operaciones que conducen a un error serio.|  
|Error|Se ha producido un error (por ejemplo, configuración no válida o comportamiento de la red) que puede producir una pérdida de funcionalidad del usuario.|  
|Advertencia|Existe una condición que puede producir como consecuencia un error o error crítico (por ejemplo, error de asignación o aproximación a un límite). El procesamiento normal de errores del código de usuario (por ejemplo, transacciones anuladas, tiempos de espera, error en la autenticación) también puede generar un mensaje de advertencia.|  
|Información|Se han generado mensajes útiles para supervisar y diagnosticar el estado del sistema, medir el rendimiento o perfilar. Éstos pueden incluir transacción e inscripción de los eventos perpetuos, como una transacción que se está creando o confirmando, el cruce de un límite significativo o la asignación de recursos significativos. Un programador puede utilizar a continuación tal información para el diseño de la capacidad y gestión de rendimiento.|  
  
## <a name="trace-codes"></a>Códigos de seguimiento  
 La tabla siguiente hace una lista de los códigos de seguimiento que se generan mediante la infraestructura <xref:System.Transactions>. Incluido en la tabla son el identificador de código de seguimiento, la <xref:System.Diagnostics.EventTypeFilter.EventType%2A> nivel de enumeración para el seguimiento y los datos adicionales incluidos en el **TraceRecord** para el seguimiento. Además, el nivel de seguimiento correspondiente del seguimiento también se almacena en la **TraceRecord**.  
  
|TraceCode|EventType|Datos adicionales en TraceRecord|  
|---------------|---------------|-------------------------------|  
|TransactionCreated|Info|TransactionTraceId|  
|TransactionPromoted|Info|TransactionTraceId local, TransactionTraceId distribuido|  
|EnlistmentCreated|Info|TransactionTraceId, EnlistmentTraceId, EnlistmentType (durable/volátil), EnlistmentOptions|  
|EnlistmentCallbackNegative|Advertencia|TransactionTraceId, EnlistmentTraceId<br /><br /> Devolución de llamada (deshecho forzado/anulado/dudoso)|  
|TransactionRollbackCalled|Advertencia|TransactionTraceId|  
|TransactionAborted|Advertencia|TransactionTraceId|  
|TransactionInDoubt|Advertencia|TransactionTraceId|  
|TransactionScopeCreated|Info|TransactionScopeResult, que puede ser lo siguientes:<br /><br /> -Nueva transacción.<br />-Se pasa transaction.<br />-Pasa la transacción dependiente.<br />-Utilizando la transacción actual.<br />-No hay ninguna transacción.<br /><br /> Nueva TransactionTraceId actual|  
|TransactionScopeDisposed|Info|TransactionTraceId de ámbito de la transacción actual "había esperado".|  
|TransactionScopeIncomplete|Advertencia|TransactionTraceId de ámbito de la transacción actual "había esperado".|  
|TransactionScopeNestedIncorrectly|Advertencia|TransactionTraceId de ámbito de la transacción actual "había esperado".|  
|TransactionScopeCurrentTransactionChanged|Advertencia|TransactionTraceId actual anterior, otro TransactionTraceId|  
|TransactionScopeTimeout|Advertencia|TransactionTraceId de ámbito de la transacción actual "había esperado".|  
|DependentCloneCreated|Info|TransactionTraceId, tipo de transacción dependiente creada (RollbackIfNotComplete/BlockCommitUntilComplete)|  
|DependentCloneComplete|Info|TransactionTraceId|  
|RecoveryComplete|Info|Recurso Administrador GUID (de la base)|  
|Reenlist|Info|Recurso Administrador GUID (de la base)|  
|TransactionSerialized|Info|TransactionTraceId.|  
|TransactionException|Error|Mensaje de la excepción|  
|InvalidOperationException|Error|Mensaje de la excepción|  
|InternalError|Crítico|Mensaje de la excepción|  
|TransferEvent||Cuando se deserializa una transacción, o se promueve una transacción <xref:System.Transactions> a uno distribuido, se escriben los ActivityID actuales de ExecutionContext y el Id. de la transacción distribuida.<br /><br /> Cuando la DTC llama de nuevo en el código administrado, el Id. de la transacción distribuida se establece como ActivityID en ExecutionContext para la duración de la devolución de llamada.|  
|ConfiguredDefaultTimeoutAdjusted|Advertencia|Ningún dato adicional|  
|TransactionTimeout|Advertencia|La TransactionTraceId de la transacción habiendo agotado el tiempo de espera.|  
  
 El esquema XML para cada uno de los elementos de datos adicionales anteriores tiene el formato siguiente.  
  
### <a name="transactiontraceidentifier"></a>TransactionTraceIdentifier  
 `<TransactionTraceIdentifier>`  
  
 `<TransactionIdentifier >`  
  
 `string representation of transaction id`  
  
 `</TransactionIdentifier>`  
  
 `< CloneIdentifier >`  
  
 `the clone id number`  
  
 `</CloneIdentifier>`  
  
 `</TransactionTraceIdentifier>`  
  
### <a name="enlistmenttraceidentifier"></a>EnlistmentTraceIdentifier  
 `<EnlistmentTraceIdentifier>`  
  
 `<ResourceManagerId>`  
  
 `string form of guid`  
  
 `</ResourceManagerId>`  
  
 `<TransactionTraceIdentifier>`  
  
 `<TransactionIdentifier >`  
  
 `string representation of transaction id`  
  
 `</TransactionIdentifier>`  
  
 `<CloneIdentifier >`  
  
 `the clone id number`  
  
 `</CloneIdentifier>`  
  
 `<TransactionTraceIdentifier>`  
  
 `<EnlistmentIdentifier>`  
  
 `the enlistment id number`  
  
 `</EnlistmentIdentifier>`  
  
 `</EnlistmentTraceIdentifier>`  
  
### <a name="resource-manager-identifier"></a>Identificador del administrador de recursos  
 `<ResourceManagerId>`  
  
 `string form of guid`  
  
 `</ResourceManagerId>`  
  
## <a name="security-issues-for-tracing"></a>Problemas de seguridad para seguir paso a paso  
 Cuando usted como administrador activa el seguimiento, la información confidencial puede escribirse en un registro de seguimiento que está visible públicamente de forma predeterminada. Para mitigar ninguna amenaza de seguridad posible, considere la posibilidad de almacenar el registro de seguimiento en una ubicación segura que se controla mediante permisos de acceso de sistema de archivos y recursos compartidos.
