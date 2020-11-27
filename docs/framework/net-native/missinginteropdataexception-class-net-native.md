---
title: Clase MissingInteropDataException (.NET Native)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: eab4bcf8-9f5f-4731-87d8-842748a6062a
ms.openlocfilehash: bbbb484e5cb8060568b321a2a41474d60c9f87f6
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96250923"
---
# <a name="missinginteropdataexception-class-net-native"></a>Clase MissingInteropDataException (.NET Native)

**.NET para aplicaciones de Windows para Windows 10, solo .NET Native**  
  
 Excepción que se genera cuando se llama a un método de cálculo de referencias manual, pero el análisis estático no encuentra metadatos para un tipo de análisis o no existen en un archivo de directivas en tiempo de ejecución.  
  
 **Espacio de nombres:** System.Runtime.CompilerServices  
  
> [!IMPORTANT]
> La `MissingInteropDataException` clase está pensada únicamente para uso interno de la cadena de herramientas de .net Native. No está pensada para usarse en código de terceros y tampoco debe usarse para controlar la excepción en el código de la aplicación. En su lugar, elimine la excepción. Para ello, agregue entradas al [archivo de directivas en tiempo de ejecución](runtime-directives-rd-xml-configuration-file-reference.md). Para obtener más información, vea la sección Comentarios.  
  
## <a name="syntax"></a>Syntax  

 [!code-csharp[ProjectN#21](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn/cs/missinginteropdataexception_syntax1.cs#21)]
 [!code-vb[ProjectN#21](../../../samples/snippets/visualbasic/VS_Snippets_CLR/projectn/vb/missinginteropdataexception_syntax1.vb#21)]  
  
 La clase `MissingInteropDataException` tiene los siguientes miembros:  
  
## <a name="constructors"></a>Constructores  
  
|Constructor|Descripción|  
|-----------------|-----------------|  
|`public MissingInteropDataException(String resourceId, Type pertinentType)`|Inicializa una nueva instancia de la clase `MissingInteropDataException` mediante el identificador de un mensaje proporcionado por el sistema que describe el error y el tipo cuyos datos faltan. Este constructor es para uso interno solo por la cadena de herramientas de .NET Native.|  
  
## <a name="properties"></a>Propiedades  
  
|Propiedad|Descripción|  
|--------------|-----------------|  
|`public IDictionary Data { get; }`|Obtiene una colección de pares clave/valor que proporciona información definida por el usuario adicional sobre la excepción. (Se hereda de <xref:System.Exception?displayProperty=nameWithType>).|  
|`public string HelpLink { get; set; }`|Obtiene o establece un vínculo al archivo de ayuda asociado a esta excepción. (Se hereda de <xref:System.Exception?displayProperty=nameWithType>).|  
|`public int HResult { get; protected set; }`|Obtiene o establece el `HRESULT`, que es un valor numérico codificado que se asigna a una excepción específica. (Se hereda de <xref:System.Exception?displayProperty=nameWithType>).|  
|`public Exception InnerException { get; }`|Obtiene la excepción que ha generado la excepción actual. (Se hereda de <xref:System.Exception?displayProperty=nameWithType>).|  
|`public string Message { get; }`|Obtiene un mensaje que describe la excepción actual. (Se hereda de <xref:System.Exception?displayProperty=nameWithType>).|  
|`public Type MissingType { get; private set; }`|Obtiene o establece el tipo cuyos datos faltan.|  
|`public string Source { get; set; }`|Obtiene o establece el nombre de la aplicación u objeto que produjo el error. (Se hereda de <xref:System.Exception?displayProperty=nameWithType>).|  
|`public string StackTrace { get; }`|Obtiene una representación de cadena de los marcos inmediatos en la pila de llamadas. (Se hereda de <xref:System.Exception?displayProperty=nameWithType>).|  
|`public MethodBase TargetSite { get; }`|Obtiene el método que generó la excepción actual. (Se hereda de <xref:System.Exception?displayProperty=nameWithType>).|  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|`public bool Equals(Object obj)`|Determina si el objeto especificado es igual que el objeto actual.  (Se hereda de <xref:System.Object>).|  
|`protected void Finalize()`|Permite que un objeto intente liberar recursos y realizar otras operaciones de limpieza antes de que sea reclamado por la recolección de elementos no utilizados. (Se hereda de <xref:System.Object>).|  
|`public Exception GetBaseException()`|Devuelve la excepción que es la causa raíz de una o más excepciones posteriores. (Se hereda de <xref:System.Exception?displayProperty=nameWithType>).|  
|`public int GetHashCode()`|Devuelve un código hash de una instancia de `MissingInteropDataException`.   (Se hereda de <xref:System.Object>).|  
|`public void GetObjectData(SerializationInfo info, StreamingContext context)`|Establece un objeto <xref:System.Runtime.Serialization.SerializationInfo> con información sobre la excepción.  (Se hereda de <xref:System.Exception?displayProperty=nameWithType>).|  
|`public Type GetType()`|Obtiene el tipo de tiempo de ejecución de la instancia actual. (Se hereda de <xref:System.Exception?displayProperty=nameWithType>).|  
|`protected Object MemberwiseClone()`|Crea una copia superficial del objeto actual. (Se hereda de <xref:System.Object>).|  
|`public string ToString()`|Devuelve la representación de cadena de la excepción actual. (Se hereda de <xref:System.Exception?displayProperty=nameWithType>).|  
  
## <a name="events"></a>Events  
  
|Evento|Descripción|  
|-----------|-----------------|  
|`protected event EventHandler<SafeSerializationEventArgs> SerializeObjectState`|Ocurre cuando una excepción se serializa para crear un objeto de estado de excepción que contenga datos serializados sobre la excepción. (Se hereda de <xref:System.Exception?displayProperty=nameWithType>).|  
  
## <a name="usage-details"></a>Detalles de uso  

 La excepción `MissingInteropDataException` se genera cuando una llamada de método a un componente COM o de Windows Runtime no se puede realizar correctamente porque no hay disponible información sobre el tipo.  
  
 Los metadatos que están disponibles para una aplicación en tiempo de ejecución se definen mediante el archivo de directivas de tiempo de ejecución (configuración XML), \*.rd.xml. Para evitar que la aplicación genere esta excepción, debe modificar este archivo para definir los metadatos que deben estar presentes en tiempo de ejecución. La forma más habitual de abordar este error consiste en agregar un atributo `MarshalObject`, `MarshalDelegate`, o `MarshalStructure` a un elemento de programa apropiado en el archivo de directivas en tiempo de ejecución. Para obtener información sobre el formato de este archivo, vea [Runtime Directives (rd.xml) Configuration File Reference](runtime-directives-rd-xml-configuration-file-reference.md) (Referencia del archivo de configuración de directivas en tiempo de ejecución (rd.xml)).  
  
> [!IMPORTANT]
> Puesto que esta excepción indica que los metadatos que la aplicación necesita no están disponibles en tiempo de ejecución, no debe controlar esta excepción en un bloque `try`/`catch`. En su lugar, debe diagnosticar la causa de la excepción y eliminarla. Para ello, agregue la entrada apropiada a un archivo de directivas en tiempo de ejecución.  
  
 La clase `MissingInteropDataException` contiene un único miembro (la propiedad `MissingType`), que señala el tipo cuyos metadatos son necesarios para poder realizar una llamada de método correctamente. El resto de miembros se hereda de la clase base, <xref:System.Exception?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Exception?displayProperty=nameWithType>
- [Clase MissingMetadataException](missingmetadataexception-class-net-native.md)
- [Referencia del archivo de configuración de directivas en tiempo de ejecución (rd.xml)](runtime-directives-rd-xml-configuration-file-reference.md)
