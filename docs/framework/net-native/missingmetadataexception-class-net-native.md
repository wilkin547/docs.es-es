---
title: Clase MissingMetadataException (.NET Native)
ms.date: 03/30/2017
ms.assetid: 408f25c4-6d60-475c-92b1-7b52b777c6db
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3955329903af0d4c27bc7228c7c9025cb03e00f8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33394318"
---
# <a name="missingmetadataexception-class-net-native"></a>Clase MissingMetadataException (.NET Native)
**.NET para aplicaciones de Windows para Windows 10, solo [!INCLUDE[net_native](../../../includes/net-native-md.md)]**  
  
 Excepción que se genera al utilizar reflexión para recuperar metadatos que no están presentes.  
  
 **Espacio de nombres:** System.Reflection  
  
> [!IMPORTANT]
>  La clase `MissingMetadataException` está diseñada únicamente para uso interno en la cadena de herramientas [!INCLUDE[net_native](../../../includes/net-native-md.md)]. No está pensada para usarse en código de terceros y tampoco debe usarse para controlar la excepción en el código de la aplicación. En su lugar, elimine la excepción. Para ello, agregue entradas al [archivo de directivas en tiempo de ejecución](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md). Para obtener más información, vea la sección Comentarios.  
  
## <a name="syntax"></a>Sintaxis  
 [!code-csharp[ProjectN#4](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn/cs/missingmetadataexception_syntax1.cs#4)]  
  
 Tenga en cuenta que la clase `MissingMetadataException` deriva de <xref:System.TypeAccessException>.  
  
 La clase `MissingMetadataException` tiene los siguientes miembros:  
  
## <a name="constructors"></a>Constructores  
  
|Constructor|Descripción|  
|-----------------|-----------------|  
|`public MissingMetadataException()`|Inicializa una nueva instancia de la clase `MissingMetadataException` mediante un mensaje proporcionado por el sistema que describe el error.<br /><br /> Este constructor es para uso interno exclusivo de la cadena de herramientas de [!INCLUDE[net_native](../../../includes/net-native-md.md)].|  
|`public MissingMetadataException(String message)`|Inicializa una nueva instancia de la clase `MissingMetadataException` con el mensaje de error especificado.<br /><br /> Este constructor es para uso interno exclusivo de la cadena de herramientas de [!INCLUDE[net_native](../../../includes/net-native-md.md)].|  
  
## <a name="properties"></a>Propiedades  
  
|Propiedad|Descripción|  
|--------------|-----------------|  
|`public IDictionary Data { get; }`|Obtiene una colección de pares clave-valor que proporcionan más información definida por el usuario sobre la excepción. (Se hereda de <xref:System.Exception?displayProperty=nameWithType>).|  
|`public string HelpLink { get; set; }`|Obtiene o establece un vínculo al archivo de ayuda asociado a esta excepción. (Se hereda de <xref:System.Exception?displayProperty=nameWithType>).|  
|`public int HResult { get; protected set; }`|Obtiene o establece el `HRESULT`, que es un valor numérico codificado que se asigna a una excepción específica. (Se hereda de <xref:System.Exception?displayProperty=nameWithType>).|  
|`public Exception InnerException { get; }`|Obtiene la excepción que ha generado la excepción actual. (Se hereda de <xref:System.Exception?displayProperty=nameWithType>).|  
|`public string Message { get; }`|Obtiene un mensaje que describe la excepción actual. (Se hereda de <xref:System.TypeLoadException>).|  
|`public string Source { get; set; }`|Obtiene o establece el nombre de la aplicación u objeto que produjo el error. (Se hereda de <xref:System.Exception?displayProperty=nameWithType>).|  
|`public string StackTrace { get; }`|Obtiene una representación de cadena de los marcos inmediatos en la pila de llamadas. (Se hereda de <xref:System.Exception?displayProperty=nameWithType>).|  
|`public MethodBase TargetSite { get; }`|Obtiene el método que generó la excepción actual. (Se hereda de <xref:System.Exception?displayProperty=nameWithType>).|  
|`public string TypeName { get; ]`|Obtiene el nombre completo del tipo cuyos metadatos faltan. (Se hereda de <xref:System.TypeLoadException>).|  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|`public bool Equals(Object obj)`|Determina si el objeto especificado es igual al objeto actual.  (Se hereda de <xref:System.Exception?displayProperty=nameWithType>).|  
|`protected void Finalize()`|Permite que un objeto intente liberar recursos y realizar otras operaciones de limpieza antes de que sea reclamado por la recolección de elementos no utilizados. (Se hereda de <xref:System.Object>).|  
|`public Exception GetBaseException()`|Devuelve la excepción que es la causa raíz de una o más excepciones posteriores. (Se hereda de <xref:System.Exception?displayProperty=nameWithType>).|  
|`public int GetHashCode()`|Devuelve un código hash de una instancia de `MissingMetadataException`.   (Se hereda de <xref:System.Object>).|  
|`public void GetObjectData(SerializationInfo info, StreamingContext context)`|Establece un objeto <xref:System.Runtime.Serialization.SerializationInfo> con información sobre la excepción.  (Se hereda de <xref:System.TypeLoadException>).|  
|`public Type GetType()`|Obtiene el tipo en tiempo de ejecución de la instancia actual. (Se hereda de <xref:System.Exception?displayProperty=nameWithType>).|  
|`protected Object MemberwiseClone()`|Crea una copia superficial del objeto actual. (Se hereda de <xref:System.Object>).|  
|`public string ToString()`|Devuelve la representación de cadena de la excepción actual. (Se hereda de <xref:System.Exception?displayProperty=nameWithType>).|  
  
## <a name="events"></a>Eventos  
  
|Evento|Descripción|  
|-----------|-----------------|  
|`protected event EventHandler<SafeSerializationEventArgs> SerializeObjectState`|Ocurre cuando una excepción se serializa para crear un objeto de estado de excepción que contenga datos serializados sobre la excepción. (Se hereda de <xref:System.Exception?displayProperty=nameWithType>).|  
  
## <a name="usage-details"></a>Detalles de uso  
 La excepción `MissingMetadataException` se produce cuando se utiliza la reflexión para acceder a los metadatos que no están disponibles en un ensamblado.  
  
 Los metadatos que hay disponibles para una aplicación en tiempo de ejecución se definen mediante el archivo de directivas en tiempo de ejecución (configuración XML), *.rd.xml. Para evitar que la aplicación genere esta excepción, debe modificar \*.rd.xml para definir los metadatos que deben estar presentes en tiempo de ejecución. Para obtener información sobre el formato del archivo \*.rd.xml, vea [Runtime Directives (rd.xml) Configuration File Reference](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md) (Referencia del archivo de configuración de directivas en tiempo de ejecución (rd.xml)).  
  
> [!IMPORTANT]
>  Puesto que esta excepción indica que los metadatos que la aplicación necesita no están disponibles en tiempo de ejecución, no debe controlar esta excepción en un bloque `try`/`catch`. En su lugar, diagnostique la causa de la excepción y elimínela mediante un archivo de directivas en tiempo de ejecución. Para obtener la entrada que se puede agregar al archivo de directivas en tiempo de ejecución que elimina la excepción, puede usar uno de estos dos solucionadores de problemas:  
>   
>  -   [Solucionador de problemas de MissingMetadataException](http://dotnet.github.io/native/troubleshooter/type.html) para los tipos.  
> -   [Solucionador de problemas de MissingMetadataException](http://dotnet.github.io/native/troubleshooter/method.html) para los métodos.  
  
 La clase `MissingMetadataException` no contiene miembros únicos, sino que todos sus miembros se heredan de la clase base <xref:System.TypeAccessException>.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Exception?displayProperty=nameWithType>  
 <xref:System.TypeAccessException>  
 [Clase MissingInteropDataException](../../../docs/framework/net-native/missinginteropdataexception-class-net-native.md)  
 [Clase MissingRuntimeArtifactException](../../../docs/framework/net-native/missingruntimeartifactexception-class-net-native.md)  
 [Runtime Directives (rd.xml) Configuration File Reference (Referencia del archivo de configuración de directivas en tiempo de ejecución (rd.xml))](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)
