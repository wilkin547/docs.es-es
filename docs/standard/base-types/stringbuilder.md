---
title: Utilizar la clase StringBuilder en .NET
description: Aprenda a utilizar la clase StringBuilder en .NET. Use esta clase para modificar una cadena sin crear un objeto.
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Remove method
- strings [.NET], capacities
- StringBuilder object
- Replace method
- AppendFormat method
- Append method
- Insert method
- strings [.NET], StringBuilder object
ms.assetid: 5c14867c-9a99-45bc-ae7f-2686700d377a
ms.openlocfilehash: 1005da650c624b2b8f6616c163082ff95d7dc007
ms.sourcegitcommit: 4a938327bad8b2e20cabd0f46a9dc50882596f13
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/28/2020
ms.locfileid: "92888963"
---
# <a name="using-the-stringbuilder-class-in-net"></a>Utilizar la clase StringBuilder en .NET
El objeto <xref:System.String> es inmutable. Cada vez que se usa uno de los métodos de la clase <xref:System.String?displayProperty=nameWithType>, se crea un objeto de cadena en la memoria, lo que requiere una nueva asignación de espacio para ese objeto. En las situaciones en las que es necesario realizar modificaciones repetidas en una cadena, la sobrecarga asociada a la creación de un objeto <xref:System.String> puede ser costosa. La clase <xref:System.Text.StringBuilder?displayProperty=nameWithType> se puede usar para modificar una cadena sin crear un objeto. Por ejemplo, el uso de la clase <xref:System.Text.StringBuilder> puede mejorar el rendimiento al concatenar muchas cadenas en un bucle.  
  
## <a name="importing-the-systemtext-namespace"></a>Importar el espacio de nombres System.Text  
 La clase <xref:System.Text.StringBuilder> se encuentra en el espacio de nombres <xref:System.Text>.  Para evitar proporcionar un nombre de tipo completo en el código, se puede importar el espacio de nombres <xref:System.Text>:  
  
 [!code-cpp[Conceptual.StringBuilder#11](../../../samples/snippets/cpp/VS_Snippets_CLR/Conceptual.StringBuilder/cpp/example.cpp#11)]
 [!code-csharp[Conceptual.StringBuilder#11](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.StringBuilder/cs/Example.cs#11)]
 [!code-vb[Conceptual.StringBuilder#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.StringBuilder/vb/Example.vb#11)]  
  
## <a name="instantiating-a-stringbuilder-object"></a>Crear instancias de un objeto StringBuilder  
 Para crear una instancia de la clase <xref:System.Text.StringBuilder>, inicialice la variable con uno de los métodos de constructor sobrecargado, como se muestra en el ejemplo siguiente.  
  
 [!code-cpp[Conceptual.StringBuilder#1](../../../samples/snippets/cpp/VS_Snippets_CLR/Conceptual.StringBuilder/cpp/example.cpp#1)]
 [!code-csharp[Conceptual.StringBuilder#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.StringBuilder/cs/Example.cs#1)]
 [!code-vb[Conceptual.StringBuilder#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.StringBuilder/vb/Example.vb#1)]  
  
## <a name="setting-the-capacity-and-length"></a>Configurar la capacidad y la longitud  
 Aunque <xref:System.Text.StringBuilder> es un objeto dinámico que permite expandir el número de caracteres de la cadena que encapsula, se puede especificar un valor para el número máximo de caracteres que puede contener. Este valor se conoce como la capacidad del objeto y no debe confundirse con la longitud de la cadena que el objeto <xref:System.Text.StringBuilder> actual contiene. Por ejemplo, puede crear una instancia de la clase <xref:System.Text.StringBuilder> con la cadena "Hello", que tiene una longitud de 5, y especificar que el objeto tiene una capacidad máxima de 25. Al modificar <xref:System.Text.StringBuilder>, este no reasigna el tamaño para sí mismo hasta que se alcanza la capacidad. Cuando esto sucede, el nuevo espacio se asigna automáticamente y se duplica la capacidad. La capacidad de la clase <xref:System.Text.StringBuilder> se puede especificar con uno de los constructores sobrecargados. En el ejemplo siguiente se especifica que el objeto `myStringBuilder` se puede expandir hasta un máximo de 25 espacios.  
  
 [!code-cpp[Conceptual.StringBuilder#2](../../../samples/snippets/cpp/VS_Snippets_CLR/Conceptual.StringBuilder/cpp/example.cpp#2)]
 [!code-csharp[Conceptual.StringBuilder#2](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.StringBuilder/cs/Example.cs#2)]
 [!code-vb[Conceptual.StringBuilder#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.StringBuilder/vb/Example.vb#2)]  
  
 Además, se puede usar la propiedad de lectura y escritura <xref:System.Text.StringBuilder.Capacity%2A> para establecer la longitud máxima del objeto. En el ejemplo siguiente se usa la propiedad **Capacity** para definir la longitud máxima del objeto.  
  
 [!code-cpp[Conceptual.StringBuilder#3](../../../samples/snippets/cpp/VS_Snippets_CLR/Conceptual.StringBuilder/cpp/example.cpp#3)]
 [!code-csharp[Conceptual.StringBuilder#3](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.StringBuilder/cs/Example.cs#3)]
 [!code-vb[Conceptual.StringBuilder#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.StringBuilder/vb/Example.vb#3)]  
  
 El método <xref:System.Text.StringBuilder.EnsureCapacity%2A> se puede usar para comprobar la capacidad del objeto **StringBuilder** actual. Si la capacidad es mayor que el valor transmitido, no se realiza ningún cambio, pero si es menor que este, la capacidad actual se cambia para que coincida con el valor en cuestión.  
  
 También se puede ver o establecer la propiedad <xref:System.Text.StringBuilder.Length%2A>. Si la propiedad **Length** se establece en un valor mayor que el de la propiedad **Capacity** , la propiedad **Capacity** se cambia automáticamente al mismo valor de la propiedad **Length** . Si la propiedad **Length** se establece en un valor menor que la longitud de la cadena de **StringBuilder** actual, se acorta la cadena.  
  
## <a name="modifying-the-stringbuilder-string"></a>Modificar la cadena StringBuilder  
 En la tabla siguiente se enumeran los métodos que se pueden usar para modificar el contenido de **StringBuilder** .  
  
|Nombre del método|Usar|  
|-----------------|---------|  
|<xref:System.Text.StringBuilder.Append%2A?displayProperty=nameWithType>|Anexa información al final del objeto **StringBuilder** actual.|  
|<xref:System.Text.StringBuilder.AppendFormat%2A?displayProperty=nameWithType>|Reemplaza a un especificador de formato que se pasa en una cadena con texto con formato|  
|<xref:System.Text.StringBuilder.Insert%2A?displayProperty=nameWithType>|Inserta una cadena o un objeto en el índice especificado del elemento **StringBuilder** actual.|  
|<xref:System.Text.StringBuilder.Remove%2A?displayProperty=nameWithType>|Quita el número de caracteres especificado del objeto **StringBuilder** actual.|  
|<xref:System.Text.StringBuilder.Replace%2A?displayProperty=nameWithType>|Reemplaza todas las apariciones de un carácter o cadena especificados en la instancia de **StringBuilder** por otro carácter o cadena especificados.|  
  
### <a name="append"></a>Anexar  
 El método **Append** se puede usar para agregar texto o la representación de cadena de un objeto al final de una cadena representada por el objeto **StringBuilder** actual. En el ejemplo siguiente, se inicializa **StringBuilder** en "Hello World" y, después, se anexa texto al final del objeto. El espacio se asigna automáticamente según sea necesario.  
  
 [!code-cpp[Conceptual.StringBuilder#4](../../../samples/snippets/cpp/VS_Snippets_CLR/Conceptual.StringBuilder/cpp/example.cpp#4)]
 [!code-csharp[Conceptual.StringBuilder#4](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.StringBuilder/cs/Example.cs#4)]
 [!code-vb[Conceptual.StringBuilder#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.StringBuilder/vb/Example.vb#4)]  
  
### <a name="appendformat"></a>AppendFormat  
 El método <xref:System.Text.StringBuilder.AppendFormat%2A?displayProperty=nameWithType> agrega texto al final del objeto <xref:System.Text.StringBuilder>. Admite la característica de formatos compuestos (para obtener más información, consulte [Formatos compuestos](composite-formatting.md)) mediante la llamada a la implementación de <xref:System.IFormattable> del objeto u objetos a los que se va a dar formato. Por tanto, acepta las cadenas de formato estándar para valores numéricos, de fecha y hora y de enumeración; las cadenas de formato personalizado para valores numéricos y de fecha y hora; y las cadenas de formato definidas para los tipos personalizados. (Para obtener información acerca del formato, consulte [Aplicar formato a tipos](formatting-types.md).) Este método se puede usar para personalizar el formato de las variables y anexar esos valores a <xref:System.Text.StringBuilder>. En el ejemplo siguiente se usa el método <xref:System.Text.StringBuilder.AppendFormat%2A> para colocar un valor entero con formato de valor de divisa al final de un objeto <xref:System.Text.StringBuilder>.  
  
 [!code-cpp[Conceptual.StringBuilder#5](../../../samples/snippets/cpp/VS_Snippets_CLR/Conceptual.StringBuilder/cpp/example.cpp#5)]
 [!code-csharp[Conceptual.StringBuilder#5](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.StringBuilder/cs/Example.cs#5)]
 [!code-vb[Conceptual.StringBuilder#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.StringBuilder/vb/Example.vb#5)]  
  
### <a name="insert"></a>Insertar  
 El método <xref:System.Text.StringBuilder.Insert%2A> agrega una cadena o un objeto en una posición especificada del objeto <xref:System.Text.StringBuilder> actual. En el ejemplo siguiente se usa este método para insertar una palabra en la sexta posición de un objeto <xref:System.Text.StringBuilder>.  
  
 [!code-cpp[Conceptual.StringBuilder#6](../../../samples/snippets/cpp/VS_Snippets_CLR/Conceptual.StringBuilder/cpp/example.cpp#6)]
 [!code-csharp[Conceptual.StringBuilder#6](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.StringBuilder/cs/Example.cs#6)]
 [!code-vb[Conceptual.StringBuilder#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.StringBuilder/vb/Example.vb#6)]  
  
### <a name="remove"></a>Quitar  
 El método **Remove** se puede usar para quitar un número de caracteres especificado del objeto <xref:System.Text.StringBuilder>, a partir de un índice de base cero definido. En el ejemplo siguiente se usa el método **Remove** para acortar un objeto <xref:System.Text.StringBuilder>.  
  
 [!code-cpp[Conceptual.StringBuilder#7](../../../samples/snippets/cpp/VS_Snippets_CLR/Conceptual.StringBuilder/cpp/example.cpp#7)]
 [!code-csharp[Conceptual.StringBuilder#7](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.StringBuilder/cs/Example.cs#7)]
 [!code-vb[Conceptual.StringBuilder#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.StringBuilder/vb/Example.vb#7)]  
  
### <a name="replace"></a>Sustituya  
 El método **Replace** se puede usar para reemplazar caracteres del objeto <xref:System.Text.StringBuilder> por otro carácter especificado. En el ejemplo siguiente se usa el método **Replace** para buscar todas las instancias del carácter de signo de exclamación (!) y reemplazarlas por el carácter de signo de interrogación (?) en un objeto <xref:System.Text.StringBuilder>.  
  
 [!code-cpp[Conceptual.StringBuilder#8](../../../samples/snippets/cpp/VS_Snippets_CLR/Conceptual.StringBuilder/cpp/example.cpp#8)]
 [!code-csharp[Conceptual.StringBuilder#8](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.StringBuilder/cs/Example.cs#8)]
 [!code-vb[Conceptual.StringBuilder#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.StringBuilder/vb/Example.vb#8)]  
  
## <a name="converting-a-stringbuilder-object-to-a-string"></a>Convertir un objeto StringBuilder en String  
 Debe convertir primero el objeto <xref:System.Text.StringBuilder> en un objeto <xref:System.String> para poder pasar la cadena representada por el objeto <xref:System.Text.StringBuilder> a un método con un parámetro <xref:System.String> o mostrarla en la interfaz de usuario. Para hacer esta conversión, llame al método <xref:System.Text.StringBuilder.ToString%2A?displayProperty=nameWithType>. En el ejemplo siguiente se llama a varios métodos de <xref:System.Text.StringBuilder> y después se llama al método <xref:System.Text.StringBuilder.ToString?displayProperty=nameWithType> para mostrar la cadena.  
  
 [!code-csharp[Conceptual.StringBuilder#10](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.StringBuilder/cs/tostringexample1.cs#10)]
 [!code-vb[Conceptual.StringBuilder#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.StringBuilder/vb/tostringexample1.vb#10)]  
  
## <a name="see-also"></a>Vea también

- <xref:System.Text.StringBuilder?displayProperty=nameWithType>
- [Operaciones básicas de cadenas](basic-string-operations.md)
- [Aplicación de formato a tipos](formatting-types.md)
