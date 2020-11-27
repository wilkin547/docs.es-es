---
title: Clase MissingRuntimeArtifactException (.NET Native)
ms.date: 03/30/2017
ms.assetid: d5b3d13e-689f-4584-8ba6-44f5167a8590
ms.openlocfilehash: 2618af8e122964d64126f945c337101cb5bbe5ae
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96250910"
---
# <a name="missingruntimeartifactexception-class-net-native"></a>Clase MissingRuntimeArtifactException (.NET Native)

**.NET para aplicaciones de Windows para Windows 10, solo .NET Native**  
  
 Excepción que se genera cuando hay disponibles metadatos para un tipo o un miembro de tipo, pero su implementación se ha quitado.  
  
 **Espacio de nombres:** System.Reflection  
  
> [!IMPORTANT]
> La `MissingRuntimeArtifactException` clase está pensada únicamente para uso interno de la cadena de herramientas de .net Native. No está pensada para usarse en código de terceros y tampoco debe usarse para controlar la excepción en el código de la aplicación. En su lugar, elimine la excepción. Para ello, agregue entradas al [archivo de directivas en tiempo de ejecución](runtime-directives-rd-xml-configuration-file-reference.md). Para obtener más información, vea la sección Comentarios.  
  
## <a name="syntax"></a>Syntax  

 [!code-csharp[ProjectN#22](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn/cs/missingruntimeartifactexception_syntax1.cs#22)]  
  
 Tenga en cuenta que la clase `MissingRuntimeArtifactException` deriva de <xref:System.MemberAccessException>.  
  
 La clase `MissingRuntimeArtifactException` tiene los siguientes miembros:  
  
## <a name="constructors"></a>Constructores  
  
|Constructor|Descripción|  
|-----------------|-----------------|  
|`public MissingRuntimeArtifactException()`|Inicializa una nueva instancia de la clase `MissingRuntimeArtifactException` mediante un mensaje proporcionado por el sistema que describe el error.<br /><br /> Este constructor es para uso interno solo por la cadena de herramientas de .NET Native.|  
|`public MissingRuntimeArtifactException(String message)`|Inicializa una nueva instancia de la clase `MissingRuntimeArtifactException` con el mensaje de error especificado.<br /><br /> Este constructor es para uso interno solo por la cadena de herramientas de .NET Native.|  
  
## <a name="properties"></a>Propiedades  
  
|Propiedad|Descripción|  
|--------------|-----------------|  
|`public IDictionary Data { get; }`|Obtiene una colección de pares clave/valor que proporciona información definida por el usuario adicional sobre la excepción. (Se hereda de <xref:System.Exception?displayProperty=nameWithType>).|  
|`public string HelpLink { get; set; }`|Obtiene o establece un vínculo al archivo de ayuda asociado a esta excepción. (Se hereda de <xref:System.Exception?displayProperty=nameWithType>).|  
|`public int HResult { get; protected set; }`|Obtiene o establece el `HRESULT`, que es un valor numérico codificado que se asigna a una excepción específica. (Se hereda de <xref:System.Exception?displayProperty=nameWithType>).|  
|`public Exception InnerException { get; }`|Obtiene la excepción que ha generado la excepción actual. (Se hereda de <xref:System.Exception?displayProperty=nameWithType>).|  
|`public string Message { get; }`|Obtiene un mensaje que describe la excepción actual. (Se hereda de <xref:System.Exception?displayProperty=nameWithType>).|  
|`public string Source { get; set; }`|Obtiene o establece el nombre de la aplicación u objeto que produjo el error. (Se hereda de <xref:System.Exception?displayProperty=nameWithType>).|  
|`public string StackTrace { get; }`|Obtiene una representación de cadena de los marcos inmediatos en la pila de llamadas. (Se hereda de <xref:System.Exception?displayProperty=nameWithType>).|  
|`public MethodBase TargetSite { get; }`|Obtiene el método que generó la excepción actual. (Se hereda de <xref:System.Exception?displayProperty=nameWithType>).|  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|`public bool Equals(Object obj)`|Determina si el objeto especificado es igual que el objeto actual.  (Se hereda de <xref:System.Object>).|  
|`protected void Finalize()`|Permite que un objeto intente liberar recursos y realizar otras operaciones de limpieza antes de que sea reclamado por la recolección de elementos no utilizados. (Se hereda de <xref:System.Object>).|  
|`public Exception GetBaseException()`|Devuelve la excepción que es la causa raíz de una o más excepciones posteriores. (Se hereda de <xref:System.Exception?displayProperty=nameWithType>).|  
|`public int GetHashCode()`|Devuelve un código hash de una instancia de `MissingRuntimeArtifactException`.   (Se hereda de <xref:System.Object>).|  
|`public void GetObjectData(SerializationInfo info, StreamingContext context)`|Establece un objeto <xref:System.Runtime.Serialization.SerializationInfo> con información sobre la excepción.  (Se hereda de <xref:System.Exception?displayProperty=nameWithType>).|  
|`public Type GetType()`|Obtiene el tipo de tiempo de ejecución de la instancia actual. (Se hereda de <xref:System.Exception?displayProperty=nameWithType>).|  
|`protected Object MemberwiseClone()`|Crea una copia superficial del objeto actual. (Se hereda de <xref:System.Object>).|  
|`public string ToString()`|Devuelve la representación de cadena de la excepción actual. (Se hereda de <xref:System.Exception?displayProperty=nameWithType>).|  
  
## <a name="events"></a>Events  
  
|Evento|Descripción|  
|-----------|-----------------|  
|`protected event EventHandler<SafeSerializationEventArgs> SerializeObjectState`|Ocurre cuando una excepción se serializa para crear un objeto de estado de excepción que contenga datos serializados sobre la excepción. (Se hereda de <xref:System.Exception?displayProperty=nameWithType>).|  
  
## <a name="usage-details"></a>Detalles de uso  

 La excepción `MissingRuntimeArtifactException` se genera cuando se intenta crear una instancia de un tipo o invocar un miembro de tipo y, aunque existen metadatos de dicho tipo o miembro, su implementación se ha quitado.  
  
 Si los metadatos y el código de implementación para ejecutar dinámicamente un método están disponibles para una aplicación en tiempo de ejecución, se define en el archivo de directivas en tiempo de ejecución (configuración XML), \*.rd.xml. Para evitar que la aplicación genere esta excepción, debe modificar \*.rd.xml para garantizar que un tipo o un miembro de tipo va a disponer de los metadatos necesarios en tiempo de ejecución. Para obtener información sobre el formato del archivo \*.rd.xml, vea [Runtime Directives (rd.xml) Configuration File Reference](runtime-directives-rd-xml-configuration-file-reference.md) (Referencia del archivo de configuración de directivas en tiempo de ejecución (rd.xml)).  
  
> [!IMPORTANT]
> Puesto que esta excepción indica que el código de implementación que la aplicación necesita no está disponible en tiempo de ejecución, no debe controlar esta excepción en un bloque `try`/`catch`. En su lugar, diagnostique la causa de la excepción y elimínela mediante un archivo de directivas en tiempo de ejecución. Normalmente, se elimina esta excepción especificando la `Activate` Directiva o adecuada `Dynamic` para un elemento de programa en el archivo de directivas en tiempo de ejecución ( \* archivo.rd.xml). Para obtener la entrada que se puede agregar al archivo de directivas en tiempo de ejecución que elimina la excepción, puede usar uno de estos dos solucionadores de problemas:  
>
> - [Solucionador de problemas de MissingMetadataException](https://dotnet.github.io/native/troubleshooter/type.html) para los tipos.  
> - [Solucionador de problemas de MissingMetadataException](https://dotnet.github.io/native/troubleshooter/method.html) para los métodos.  
  
 La clase `MissingRuntimeArtifactException` no contiene ningún miembro único; todos sus miembros se heredan de la clase base, <xref:System.MemberAccessException>.  
  
## <a name="see-also"></a>Vea también

- [Referencia del archivo de configuración de directivas en tiempo de ejecución (rd.xml)](runtime-directives-rd-xml-configuration-file-reference.md)
- [Configuración de directiva de la directiva en tiempo de ejecución](runtime-directive-policy-settings.md)
