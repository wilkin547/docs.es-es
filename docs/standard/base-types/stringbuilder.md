---
title: Utilizar la clase StringBuilder en .NET
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Remove method
- strings [.NET Framework], capacities
- StringBuilder object
- Replace method
- AppendFormat method
- Append method
- Insert method
- strings [.NET Framework], StringBuilder object
ms.assetid: 5c14867c-9a99-45bc-ae7f-2686700d377a
caps.latest.revision: "21"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 3a6c8f6dee9f2a1da6ed4a8219c1b4832464d9aa
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="using-the-stringbuilder-class-in-net"></a>Utilizar la clase StringBuilder en .NET
La <xref:System.String> objeto es inmutable. Cada vez que utilice uno de los métodos en la <xref:System.String?displayProperty=nameWithType> (clase), crear un nuevo objeto de cadena en la memoria, lo que requiere una nueva asignación de espacio para ese objeto. En situaciones donde es necesario realizar modificaciones repetidas en una cadena, la sobrecarga asociada a la creación de un nuevo <xref:System.String> objeto puede disminuir el rendimiento. La <xref:System.Text.StringBuilder?displayProperty=nameWithType> clase se puede utilizar cuando desea modificar una cadena sin crear un nuevo objeto. Por ejemplo, si se usa el <xref:System.Text.StringBuilder> clase puede mejorar el rendimiento al concatenar muchas cadenas en un bucle.  
  
## <a name="importing-the-systemtext-namespace"></a>Importar el espacio de nombres System.Text  
 El <xref:System.Text.StringBuilder> clase se encuentra en la <xref:System.Text> espacio de nombres.  Para evitar tener que proporcionar un nombre de tipo completo en el código, se puede importar el <xref:System.Text> espacio de nombres:  
  
 [!code-cpp[Conceptual.StringBuilder#11](../../../samples/snippets/cpp/VS_Snippets_CLR/Conceptual.StringBuilder/cpp/example.cpp#11)]
 [!code-csharp[Conceptual.StringBuilder#11](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.StringBuilder/cs/Example.cs#11)]
 [!code-vb[Conceptual.StringBuilder#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.StringBuilder/vb/Example.vb#11)]  
  
## <a name="instantiating-a-stringbuilder-object"></a>Crear instancias de un objeto StringBuilder  
 Puede crear una nueva instancia de la <xref:System.Text.StringBuilder> (clase), inicialice la variable con uno de los métodos de constructor sobrecargado, como se muestra en el ejemplo siguiente.  
  
 [!code-cpp[Conceptual.StringBuilder#1](../../../samples/snippets/cpp/VS_Snippets_CLR/Conceptual.StringBuilder/cpp/example.cpp#1)]
 [!code-csharp[Conceptual.StringBuilder#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.StringBuilder/cs/Example.cs#1)]
 [!code-vb[Conceptual.StringBuilder#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.StringBuilder/vb/Example.vb#1)]  
  
## <a name="setting-the-capacity-and-length"></a>Configurar la capacidad y la longitud  
 Aunque el <xref:System.Text.StringBuilder> es un objeto dinámico que permite expandir el número de caracteres de la cadena que encapsula, se puede especificar un valor para el número máximo de caracteres que puede contener. Este valor se conoce como la capacidad del objeto y no debe confundirse con la longitud de la cadena que actual <xref:System.Text.StringBuilder> contiene. Por ejemplo, podría crear una nueva instancia de la <xref:System.Text.StringBuilder> clase con la cadena "Hello", que tiene una longitud de 5 y podría especificar que el objeto tiene una capacidad máxima de 25. Cuando se modifica la <xref:System.Text.StringBuilder>, este no reasigna el tamaño para sí mismo hasta que se alcanza la capacidad. Cuando esto sucede, el nuevo espacio se asigna automáticamente y se duplica la capacidad. Puede especificar la capacidad de la <xref:System.Text.StringBuilder> mediante uno de los constructores sobrecargados de la clase. En el ejemplo siguiente se especifica que el objeto `MyStringBuilder` se puede expandir hasta un máximo de 25 espacios.  
  
 [!code-cpp[Conceptual.StringBuilder#2](../../../samples/snippets/cpp/VS_Snippets_CLR/Conceptual.StringBuilder/cpp/example.cpp#2)]
 [!code-csharp[Conceptual.StringBuilder#2](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.StringBuilder/cs/Example.cs#2)]
 [!code-vb[Conceptual.StringBuilder#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.StringBuilder/vb/Example.vb#2)]  
  
 Además, puede usar el modo de lectura-escritura <xref:System.Text.StringBuilder.Capacity%2A> propiedad para establecer la longitud máxima del objeto. En el ejemplo siguiente se usa la propiedad **Capacity** para definir la longitud máxima del objeto.  
  
 [!code-cpp[Conceptual.StringBuilder#3](../../../samples/snippets/cpp/VS_Snippets_CLR/Conceptual.StringBuilder/cpp/example.cpp#3)]
 [!code-csharp[Conceptual.StringBuilder#3](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.StringBuilder/cs/Example.cs#3)]
 [!code-vb[Conceptual.StringBuilder#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.StringBuilder/vb/Example.vb#3)]  
  
 El <xref:System.Text.StringBuilder.EnsureCapacity%2A> método se puede utilizar para comprobar la capacidad del elemento actual **StringBuilder**. Si la capacidad es mayor que el valor transmitido, no se realiza ningún cambio, pero si es menor que este, la capacidad actual se cambia para que coincida con el valor en cuestión.  
  
 El <xref:System.Text.StringBuilder.Length%2A> propiedad también se puede ver o establecer. Si la propiedad **Length** se establece en un valor mayor que el de la propiedad **Capacity**, la propiedad **Capacity** se cambia automáticamente al mismo valor de la propiedad **Length**. Si la propiedad **Length** se establece en un valor menor que la longitud de la cadena de **StringBuilder** actual, se acorta la cadena.  
  
## <a name="modifying-the-stringbuilder-string"></a>Modificar la cadena StringBuilder  
 En la tabla siguiente se enumeran los métodos que se pueden usar para modificar el contenido de **StringBuilder**.  
  
|Nombre del método|Uso|  
|-----------------|---------|  
|<xref:System.Text.StringBuilder.Append%2A?displayProperty=nameWithType>|Anexa información al final del objeto **StringBuilder** actual.|  
|<xref:System.Text.StringBuilder.AppendFormat%2A?displayProperty=nameWithType>|Reemplaza a un especificador de formato que se pasa en una cadena con texto con formato|  
|<xref:System.Text.StringBuilder.Insert%2A?displayProperty=nameWithType>|Inserta una cadena o un objeto en el índice especificado del elemento **StringBuilder** actual.|  
|<xref:System.Text.StringBuilder.Remove%2A?displayProperty=nameWithType>|Quita el número de caracteres especificado del objeto **StringBuilder** actual.|  
|<xref:System.Text.StringBuilder.Replace%2A?displayProperty=nameWithType>|Reemplaza un carácter concreto en un índice especificado.|  
  
### <a name="append"></a>Anexar  
 El **anexado** método se puede utilizar para agregar texto o una representación de cadena de un objeto al final de una cadena representada por el actual **StringBuilder**. En el ejemplo siguiente, se inicializa **StringBuilder** en "Hello World" y, después, se anexa texto al final del objeto. El espacio se asigna automáticamente según sea necesario.  
  
 [!code-cpp[Conceptual.StringBuilder#4](../../../samples/snippets/cpp/VS_Snippets_CLR/Conceptual.StringBuilder/cpp/example.cpp#4)]
 [!code-csharp[Conceptual.StringBuilder#4](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.StringBuilder/cs/Example.cs#4)]
 [!code-vb[Conceptual.StringBuilder#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.StringBuilder/vb/Example.vb#4)]  
  
### <a name="appendformat"></a>AppendFormat  
 El <xref:System.Text.StringBuilder.AppendFormat%2A?displayProperty=nameWithType> método agrega texto al final de la <xref:System.Text.StringBuilder> objeto. Admite la característica de formato compuesto (para obtener más información, consulte [formatos compuestos](../../../docs/standard/base-types/composite-formatting.md)) mediante una llamada a la <xref:System.IFormattable> implementación del objeto u objetos a tener el formato. Por tanto, acepta las cadenas de formato estándar para valores numéricos, de fecha y hora y de enumeración; las cadenas de formato personalizado para valores numéricos y de fecha y hora; y las cadenas de formato definidas para los tipos personalizados. (Para obtener información acerca del formato, consulte [Aplicar formato a tipos](../../../docs/standard/base-types/formatting-types.md).) Puede utilizar este método para personalizar el formato de variables y anexar esos valores a un <xref:System.Text.StringBuilder>. En el ejemplo siguiente se usa el <xref:System.Text.StringBuilder.AppendFormat%2A> método para colocar un valor entero con formato como un valor de moneda al final de una <xref:System.Text.StringBuilder> objeto.  
  
 [!code-cpp[Conceptual.StringBuilder#5](../../../samples/snippets/cpp/VS_Snippets_CLR/Conceptual.StringBuilder/cpp/example.cpp#5)]
 [!code-csharp[Conceptual.StringBuilder#5](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.StringBuilder/cs/Example.cs#5)]
 [!code-vb[Conceptual.StringBuilder#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.StringBuilder/vb/Example.vb#5)]  
  
### <a name="insert"></a>Insertar  
 El <xref:System.Text.StringBuilder.Insert%2A> método agrega una cadena u objeto en una posición especificada en este <xref:System.Text.StringBuilder> objeto. En el ejemplo siguiente se utiliza este método para insertar una palabra en la sexta posición de un <xref:System.Text.StringBuilder> objeto.  
  
 [!code-cpp[Conceptual.StringBuilder#6](../../../samples/snippets/cpp/VS_Snippets_CLR/Conceptual.StringBuilder/cpp/example.cpp#6)]
 [!code-csharp[Conceptual.StringBuilder#6](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.StringBuilder/cs/Example.cs#6)]
 [!code-vb[Conceptual.StringBuilder#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.StringBuilder/vb/Example.vb#6)]  
  
### <a name="remove"></a>Quitar  
 Puede usar el **quitar** método para quitar un número especificado de caracteres de la actual <xref:System.Text.StringBuilder> objeto, comenzando por un índice de base cero especificado. En el ejemplo siguiente se usa el **quitar** método para acortar un <xref:System.Text.StringBuilder> objeto.  
  
 [!code-cpp[Conceptual.StringBuilder#7](../../../samples/snippets/cpp/VS_Snippets_CLR/Conceptual.StringBuilder/cpp/example.cpp#7)]
 [!code-csharp[Conceptual.StringBuilder#7](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.StringBuilder/cs/Example.cs#7)]
 [!code-vb[Conceptual.StringBuilder#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.StringBuilder/vb/Example.vb#7)]  
  
### <a name="replace"></a>Reemplazar  
 El **reemplazar** método se puede utilizar para reemplazar caracteres dentro de la <xref:System.Text.StringBuilder> objeto con otro carácter especificado. En el ejemplo siguiente se usa el **reemplazar** método para buscar un <xref:System.Text.StringBuilder> objeto para todas las instancias de exclamación (!) de caracteres y reemplácelas con el carácter de signo de interrogación (?).  
  
 [!code-cpp[Conceptual.StringBuilder#8](../../../samples/snippets/cpp/VS_Snippets_CLR/Conceptual.StringBuilder/cpp/example.cpp#8)]
 [!code-csharp[Conceptual.StringBuilder#8](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.StringBuilder/cs/Example.cs#8)]
 [!code-vb[Conceptual.StringBuilder#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.StringBuilder/vb/Example.vb#8)]  
  
## <a name="converting-a-stringbuilder-object-to-a-string"></a>Convertir un objeto StringBuilder en String  
 Debe convertir el <xref:System.Text.StringBuilder> el objeto a un <xref:System.String> objeto antes de pasar la cadena representada por la <xref:System.Text.StringBuilder> objeto a un método que tiene un <xref:System.String> parámetro o mostrarlo en la interfaz de usuario. Para hacer esta conversión mediante una llamada a la <xref:System.Text.StringBuilder.ToString%2A?displayProperty=nameWithType> método. En el ejemplo siguiente se llama a un número de <xref:System.Text.StringBuilder> métodos y, a continuación, llama el <xref:System.Text.StringBuilder.ToString?displayProperty=nameWithType> método para mostrar la cadena.  
  
 [!code-csharp[Conceptual.StringBuilder#10](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.StringBuilder/cs/tostringexample1.cs#10)]
 [!code-vb[Conceptual.StringBuilder#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.StringBuilder/vb/tostringexample1.vb#10)]  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Text.StringBuilder?displayProperty=nameWithType>  
 [Operaciones básicas de cadenas](../../../docs/standard/base-types/basic-string-operations.md)  
 [Aplicación de formato a tipos](../../../docs/standard/base-types/formatting-types.md)
