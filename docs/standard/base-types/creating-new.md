---
title: "Crear cadenas nuevas en .NET Framework | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Concat (método)"
  - "CopyTo (método)"
  - "Format (método)"
  - "Insert (método)"
  - "Join (método)"
  - "cadenas [.NET Framework], crear"
ms.assetid: 06fdf123-2fac-4459-8904-eb48ab908a30
caps.latest.revision: 11
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 11
---
# Crear cadenas nuevas en .NET Framework
[!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] permite crear cadenas utilizando asignaciones simples; también sobrecarga un constructor de clases para que permita la creación de cadenas utilizando varios parámetros diferentes.  [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] proporciona también varios métodos de la clase <xref:System.String?displayProperty=fullName> que crean nuevos objetos de cadena combinando varias cadenas, matrices de cadenas y objetos.  
  
## Crear cadenas utilizando asignaciones  
 El modo más fácil de crear un nuevo objeto <xref:System.String> consiste sencillamente en asignar un literal de cadena a un objeto <xref:System.String>.  
  
## Crear cadenas utilizando un constructor de clases  
 Puede utilizar sobrecargas del constructor de clases <xref:System.String> para crear cadenas a partir de matrices de caracteres.  También puede crear una nueva cadena duplicando un determinado carácter un número específico de veces.  
  
## Métodos que devuelven cadenas  
 En la tabla siguiente se enumeran algunos métodos útiles que devuelven nuevos objetos de cadena.  
  
|Nombre del método|Utilice|  
|-----------------------|-------------|  
|<xref:System.String.Format%2A?displayProperty=fullName>|Compila una cadena con formato a partir de un conjunto de objetos de entrada.|  
|<xref:System.String.Concat%2A?displayProperty=fullName>|Compila cadenas a partir de dos o más cadenas.|  
|<xref:System.String.Join%2A?displayProperty=fullName>|Compila una nueva cadena combinando una matriz de cadenas.|  
|<xref:System.String.Insert%2A?displayProperty=fullName>|Compila una nueva cadena mediante la inserción de una cadena en el índice especificado de una cadena existente.|  
|<xref:System.String.CopyTo%2A?displayProperty=fullName>|Copia los caracteres especificados de una cadena en la posición especificada de una matriz de caracteres.|  
  
### Formato  
 El método **String.Format** se puede usar para crear cadenas con formato y concatenar cadenas que representan varios objetos.  Este método convierte automáticamente en cadena cualquier objeto que se pase.  Por ejemplo, si la aplicación debe mostrar al usuario un valor **Int32** y un valor **DateTime**, es muy sencillo construir una cadena que represente estos valores con el método **Format**.  Para obtener más información sobre las convenciones de formato utilizadas con este método, vea la sección [Formato compuesto](../../../docs/standard/base-types/composite-formatting.md).  
  
 En el ejemplo siguiente se utiliza el método **Format** para crear una cadena que usa una variable de entero.  
  
 [!code-csharp[Strings.Creating#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Strings.Creating/cs/Example.cs#1)]
 [!code-vb[Strings.Creating#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Strings.Creating/vb/Example.vb#1)]  
  
 En este ejemplo, <xref:System.DateTime.Now%2A?displayProperty=fullName> muestra la fecha y hora actual en un formato especificado por la referencia cultural asociada al subproceso actual.  
  
### Concat  
 El método **String.Concat** se puede utilizar para crear fácilmente un nuevo objeto de cadena a partir de dos o más objetos.  Proporciona una forma de concatenar cadenas independiente del lenguaje.  Este método acepta cualquier clase que se derive de **System.Object**.  En el ejemplo siguiente se crea una cadena a partir de dos objetos de cadena existentes y un carácter de separación.  
  
 [!code-csharp[Strings.Creating#2](../../../samples/snippets/csharp/VS_Snippets_CLR/Strings.Creating/cs/Example.cs#2)]
 [!code-vb[Strings.Creating#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Strings.Creating/vb/Example.vb#2)]  
  
### Join  
 El método **String.Join** crea una nueva cadena a partir de una matriz de cadenas y una cadena separadora.  Este método resulta útil si se desea concatenar varias cadenas, formando una lista que puede estar separada por una coma.  
  
 En el ejemplo siguiente se utiliza un espacio para enlazar una matriz de cadenas.  
  
 [!code-csharp[Strings.Creating#3](../../../samples/snippets/csharp/VS_Snippets_CLR/Strings.Creating/cs/Example.cs#3)]
 [!code-vb[Strings.Creating#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Strings.Creating/vb/Example.vb#3)]  
  
### Insertar  
 El método **String.Insert** crea una nueva cadena insertando una cadena en una posición específica en otra cadena.  Este método utiliza un índice basado en cero.  En el ejemplo siguiente se inserta una cadena en la quinta posición de índice de `MyString` y se crea una nueva cadena con este valor.  
  
 [!code-csharp[Strings.Creating#4](../../../samples/snippets/csharp/VS_Snippets_CLR/Strings.Creating/cs/Example.cs#4)]
 [!code-vb[Strings.Creating#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Strings.Creating/vb/Example.vb#4)]  
  
### CopyTo  
 El método **String.CopyTo** copia partes de una cadena en una matriz de caracteres.  Se puede especificar el índice inicial de la cadena y el número de caracteres que se van a copiar.  Este método toma el índice de origen, una matriz de caracteres, el índice de destino y el número de caracteres que se van a copiar.  Todos los índices se basan en cero.  
  
 En el ejemplo siguiente se usa el método **CopyTo** para copiar los caracteres de la palabra "Hello" de un objeto de cadena en la primera posición de índice de una matriz de caracteres.  
  
 [!code-csharp[Strings.Creating#5](../../../samples/snippets/csharp/VS_Snippets_CLR/Strings.Creating/cs/Example.cs#5)]
 [!code-vb[Strings.Creating#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Strings.Creating/vb/Example.vb#5)]  
  
## Vea también  
 [Operaciones básicas de cadenas](../../../docs/standard/base-types/basic-string-operations.md)   
 [Formatos compuestos](../../../docs/standard/base-types/composite-formatting.md)