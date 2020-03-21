---
title: API basada en la reflexión
ms.date: 03/30/2017
ms.assetid: f9532629-6594-4a41-909f-d083f30a42f3
ms.openlocfilehash: 1d8daceb6b744b984f86b011ad7952d0da583a79
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79181088"
---
# <a name="apis-that-rely-on-reflection"></a>API basada en la reflexión
En algunos casos, el uso de la reflexión en el código no es obvio, por lo que la cadena de herramientas de .NET Native no conserva los metadatos que se necesitan en tiempo de ejecución. En este tema se abordan algunas de las API comunes o patrones de programación habituales que no se consideran parte de la API de reflexión, pero que hacen uso de la reflexión para ejecutarse correctamente. Si los usa en su código fuente, puede agregar información sobre ellos en el archivo de directivas en tiempo de ejecución (.rd.xml) para que las llamadas a estas API no generen una excepción [MissingMetadataException](missingmetadataexception-class-net-native.md) u otra excepción en tiempo de ejecución.  
  
## <a name="typemakegenerictype-method"></a>Método Type.MakeGenericType  
 Puede crear dinámicamente instancias de un tipo genérico `AppClass<T>` llamando al método <xref:System.Type.MakeGenericType%2A?displayProperty=nameWithType> mediante código como el siguiente:  
  
 [!code-csharp[ProjectN#1](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn/cs/type_makegenerictype1.cs#1)]  
  
 Para que este código se ejecute correctamente en tiempo de ejecución, son necesarios varios elementos de metadatos. El primero son metadatos de `Browse` para el tipo genérico sin instancia, `AppClass<T>`:  
  
```xml  
<Type Name="App1.AppClass`1" Browse="Required PublicAndInternal" />  
```  
  
 Esto permite que la llamada al método <xref:System.Type.GetType%28System.String%2CSystem.Boolean%29?displayProperty=nameWithType> se realice correctamente y devuelva un objeto <xref:System.Type> válido.  
  
 Sin embargo, aun cuando se agreguen metadatos para el tipo genérico sin instancia, la llamada al método <xref:System.Type.MakeGenericType%2A?displayProperty=nameWithType> genera una excepción [MissingMetadataException](missingmetadataexception-class-net-native.md):  
  
Esta operación no se puede llevar a cabo ya que los metadatos para el tipo siguiente se quitaron por motivos de rendimiento:  
  
`App1.AppClass`1<System.Int32>'.  
  
 Puede incluir la siguiente directiva en tiempo de ejecución al archivo de directivas en tiempo de ejecución para agregar metadatos de `Activate` para la creación específica de instancias sobre `AppClass<T>` de <xref:System.Int32?displayProperty=nameWithType>:  
  
```xml  
<TypeInstantiation Name="App1.AppClass" Arguments="System.Int32"
                   Activate="Required Public" />  
```  
  
 Cada creación de instancias diferente sobre `AppClass<T>` requiere una directiva particular si se está creando con el método <xref:System.Type.MakeGenericType%2A?displayProperty=nameWithType> y no se usa de forma estática.  
  
## <a name="methodinfomakegenericmethod-method"></a>Método MethodInfo.MakeGenericMethod  
 Dada una clase `Class1` con un método genérico `GetMethod<T>(T t)`, se puede invocar a `GetMethod` mediante reflexión con código como el siguiente:  
  
 [!code-csharp[ProjectN#2](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn/cs/makegenericmethod1.cs#2)]  
  
 Para ejecutarse correctamente, este código requiere varios elementos de metadatos:  
  
- Metadatos de `Browse` para el tipo cuyo método se quiere llamar.  
  
- Metadatos de `Browse` para el método que se quiere llamar.  Si se trata de un método público, la adición de metadatos de `Browse` públicos para el tipo contenedor incluye también el método.  
  
- Metadatos dinámicos para el método al que desea llamar, de modo que la cadena de herramientas de .NET Native no quite el delegado de invocación de reflexión. Si no hay metadatos dinámicos para el método, se generará la siguiente excepción cuando se llame al método <xref:System.Reflection.MethodInfo.MakeGenericMethod%2A?displayProperty=nameWithType>:  
  
    ```output
    MakeGenericMethod() cannot create this generic method instantiation because the instantiation was not metadata-enabled: 'App1.Class1.GenMethod<Int32>(Int32)'.  
    ```  
  
 Las siguientes directivas en tiempo de ejecución procuran que estén disponibles todos los metadatos necesarios:  
  
```xml  
<Type Name="App1.Class1" Browse="Required PublicAndInternal">  
   <MethodInstantiation Name="GenMethod" Arguments="System.Int32" Dynamic="Required"/>  
</Type>  
```  
  
 Se necesita una directiva `MethodInstantiation` por cada creación de instancia diferente del método que se invoca dinámicamente, y el elemento `Arguments` se actualiza para reflejar cada argumento de creación de instancia diferente.  
  
## <a name="arraycreateinstance-and-typemaketypearray-methods"></a>Métodos Array.CreateInstance y Type.MakeTypeArray  
 En el siguiente ejemplo se llama a los métodos <xref:System.Type.MakeArrayType%2A?displayProperty=nameWithType> y <xref:System.Array.CreateInstance%2A?displayProperty=nameWithType> en un tipo, `Class1`.  
  
 [!code-csharp[ProjectN#3](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn/cs/array1.cs#3)]  
  
 Si no hay metadatos de matriz presentes, se produce el siguiente error:  
  
```output
This operation cannot be carried out as metadata for the following type was removed for performance reasons:  
  
App1.Class1[]  
  
Unfortunately, no further information is available.  
```  
  
 Se necesitan metadatos de `Browse` para el tipo de matriz para poder crear instancia de esta dinámicamente.  La siguiente directiva en tiempo de ejecución permite la creación dinámica instancias de `Class1[]`.  
  
```xml  
<Type Name="App1.Class1[]" Browse="Required Public" />  
```  
  
## <a name="see-also"></a>Consulte también

- [Introducción](getting-started-with-net-native.md)
- [Runtime Directives (rd.xml) Configuration File Reference (Referencia del archivo de configuración de directivas en tiempo de ejecución (rd.xml))](runtime-directives-rd-xml-configuration-file-reference.md)
