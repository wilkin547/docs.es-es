---
title: Creación de cadenas en .NET
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- CopyTo method
- Join method
- Format method
- Concat method
- strings [.NET Framework], creating
- Insert method
ms.assetid: 06fdf123-2fac-4459-8904-eb48ab908a30
ms.openlocfilehash: ef65c50111d6ba91ab70d0b9c8cb90c606f9366c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "73103826"
---
# <a name="creating-new-strings-in-net"></a>Creación de cadenas en .NET
.NET Framework permite crear cadenas mediante asignaciones simples y además sobrecarga un constructor de clases para admitir la creación de cadenas con una serie de parámetros distintos. .NET Framework también proporciona varios métodos en la clase <xref:System.String?displayProperty=nameWithType> que crean nuevos objetos de cadena al combinar varias cadenas, matrices de cadenas u objetos.  
  
## <a name="creating-strings-using-assignment"></a>Creación de cadenas mediante asignaciones  
 La manera más sencilla de crear un objeto <xref:System.String> es asignar un literal de cadena a un objeto <xref:System.String>.  
  
## <a name="creating-strings-using-a-class-constructor"></a>Creación de cadenas mediante un constructor de clase  
 Puede usar las sobrecargas del constructor de clases <xref:System.String> para crear cadenas a partir de matrices de caracteres. También puede crear una nueva cadena al duplicar un determinado carácter un número especificado de veces.  
  
## <a name="methods-that-return-strings"></a>Métodos que devuelven cadenas  
 En la tabla siguiente se enumeran varios métodos útiles que devuelven nuevos objetos de cadena.  
  
|Nombre del método|Usar|  
|-----------------|---------|  
|<xref:System.String.Format%2A?displayProperty=nameWithType>|Compila una cadena con formato a partir de un conjunto de objetos de entrada.|  
|<xref:System.String.Concat%2A?displayProperty=nameWithType>|Compila cadenas a partir de dos o más cadenas.|  
|<xref:System.String.Join%2A?displayProperty=nameWithType>|Compila una nueva cadena al combinar una matriz de cadenas.|  
|<xref:System.String.Insert%2A?displayProperty=nameWithType>|Compila una nueva cadena al insertar una cadena en el índice especificado de una cadena existente.|  
|<xref:System.String.CopyTo%2A?displayProperty=nameWithType>|Copia los caracteres especificados de una cadena en la posición especificada de una matriz de caracteres.|  
  
### <a name="format"></a>Formato  
 Puede usar el método **String.Format** para crear cadenas con formato y concatenar cadenas que representan a varios objetos. Este método convierte automáticamente cualquier objeto pasado en una cadena. Por ejemplo, si la aplicación debe mostrar un valor **Int32** y un valor **DateTime** al usuario, puede construir fácilmente una cadena para representar estos valores con el método **Format**. Para más información sobre las convenciones de formato usadas con este método, consulte la sección sobre [formatos compuestos](../../../docs/standard/base-types/composite-formatting.md).  
  
 En el ejemplo siguiente se usa el método **Format** para crear una cadena que emplea una variable de entero.  
  
 [!code-csharp[Strings.Creating#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Strings.Creating/cs/Example.cs#1)]
 [!code-vb[Strings.Creating#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Strings.Creating/vb/Example.vb#1)]  
  
 En este ejemplo, <xref:System.DateTime.Now%2A?displayProperty=nameWithType> muestra la fecha y hora actuales en el formato especificado por la referencia cultural asociada al subproceso actual.  
  
### <a name="concat"></a>Concat  
 El método **String.Concat** se puede usar para crear fácilmente un objeto de cadena a partir de dos o más objetos existentes. Proporciona una manera independiente del lenguaje de concatenar cadenas. Este método acepta cualquier clase que derive de **System.Object**. En el ejemplo siguiente se crea una cadena a partir de dos objetos de cadena existentes y un carácter de separación.  
  
 [!code-csharp[Strings.Creating#2](../../../samples/snippets/csharp/VS_Snippets_CLR/Strings.Creating/cs/Example.cs#2)]
 [!code-vb[Strings.Creating#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Strings.Creating/vb/Example.vb#2)]  
  
### <a name="join"></a>Join  
 El método **String.Join** crea una cadena a partir de una matriz de cadenas y una cadena separadora. Este método resulta útil si quiere concatenar varias cadenas para formar una lista quizás separada por una coma.  
  
 En el ejemplo siguiente se usa un espacio para enlazar una matriz de cadenas.  
  
 [!code-csharp[Strings.Creating#3](../../../samples/snippets/csharp/VS_Snippets_CLR/Strings.Creating/cs/Example.cs#3)]
 [!code-vb[Strings.Creating#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Strings.Creating/vb/Example.vb#3)]  
  
### <a name="insert"></a>Insertar  
 El método **String.Insert** crea una cadena al insertar una cadena en la posición especificada de otra cadena. Este método usa un índice basado en cero. En el ejemplo siguiente se inserta una cadena en la quinta posición del índice de `MyString` y se crea una nueva cadena con este valor.  
  
 [!code-csharp[Strings.Creating#4](../../../samples/snippets/csharp/VS_Snippets_CLR/Strings.Creating/cs/Example.cs#4)]
 [!code-vb[Strings.Creating#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Strings.Creating/vb/Example.vb#4)]  
  
### <a name="copyto"></a>CopyTo  
 El método **String.CopyTo** copia partes de una cadena en una matriz de caracteres. Puede especificar el índice inicial de la cadena y el número de caracteres que se va a copiar. Este método toma el índice de origen, una matriz de caracteres, el índice de destino y el número de caracteres que se va a copiar. Todos los índices se basan en cero.  
  
 En el ejemplo siguiente se usa el método **CopyTo** para copiar los caracteres de la palabra "Hello" de un objeto de cadena en la primera posición del índice de una matriz de caracteres.  
  
 [!code-csharp[Strings.Creating#5](../../../samples/snippets/csharp/VS_Snippets_CLR/Strings.Creating/cs/Example.cs#5)]
 [!code-vb[Strings.Creating#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Strings.Creating/vb/Example.vb#5)]  
  
## <a name="see-also"></a>Vea también

- [Operaciones básicas de cadenas](../../../docs/standard/base-types/basic-string-operations.md)
- [Formatos compuestos](../../../docs/standard/base-types/composite-formatting.md)
