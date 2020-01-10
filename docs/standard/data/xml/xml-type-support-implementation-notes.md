---
title: Notas de implementación de la compatibilidad con tipos XML
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: 26b071f3-1261-47ef-8690-0717f5cd93c1
ms.openlocfilehash: 40ab0f746ef82ccd195fc6b873f5c8edb255f868
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75709873"
---
# <a name="xml-type-support-implementation-notes"></a>Notas de implementación de la compatibilidad con tipos XML
En este tema se describen algunos detalles de la implementación que debería conocer.  
  
## <a name="list-mappings"></a>Asignaciones de listas  
 Los tipos <xref:System.Collections.IList>, <xref:System.Collections.ICollection>, <xref:System.Collections.IEnumerable>, **Type[]** y <xref:System.String> se utilizan para representar tipos de listas del lenguaje de definición de esquema XML (XSD).  
  
## <a name="union-mappings"></a>Asignaciones de uniones  
 Los tipos de uniones se representan mediante el tipo <xref:System.Xml.Schema.XmlAtomicValue> o <xref:System.String>. Por lo tanto, el tipo de origen o el tipo de destino deben ser siempre <xref:System.String> o <xref:System.Xml.Schema.XmlAtomicValue>.  
  
 Si el objeto <xref:System.Xml.Schema.XmlSchemaDatatype> representa un tipo de lista, dicho objeto convierte el valor de la cadena de entrada en una lista de uno o más objetos. Si <xref:System.Xml.Schema.XmlSchemaDatatype> representa un tipo de unión, se realiza un intento de analizar el valor de entrada como un tipo de miembro de la unión. Si el intento de análisis produce un error, se intenta realizar la conversión con el siguiente miembro de la unión y así sucesivamente, hasta que la conversión se realice correctamente o no haya ningún otro tipo de miembro que probar, en cuyo caso se inicia una excepción.  
  
## <a name="differences-between-clr-and-xml-data-types"></a>Diferencias entre tipos de datos XML y CLR  
 A continuación se describen determinadas diferencias que se podrían producir entre los tipos de datos XML y los tipos CLR y cómo se tratan.  
  
> [!NOTE]
> El prefijo `xs` está asignado a <https://www.w3.org/2001/XMLSchema> y al URI del espacio de nombres.
  
### <a name="systemtimespan-and-xsduration"></a>System.TimeSpan y xs:duration  
 El tipo `xs:duration` está parcialmente ordenado, ya que hay determinados valores de duración que son diferentes, pero equivalentes. Eso significa que para el valor del tipo `xs:duration`, por ejemplo 1 mes (P1M), es menor que 32 días (P32D), mayor que 27 días (P27D) y equivalente a 28, 29 o 30 días.  
  
 La clase <xref:System.TimeSpan> no admite esta ordenación parcial. En su lugar, toma un número de días específico para 1 año y 1 mes; 365 días y 30 días, respectivamente.  
  
 Para más información sobre el tipo `xs:duration`, vea la [recomendación de W3C sobre la parte 2 del esquema XML relacionada con los tipos de datos](https://www.w3.org/TR/xmlschema-2/).
  
### <a name="xstime-gregorian-date-types-and-systemdatetime"></a>xs:time, tipos de fechas gregorianas y System.DateTime  
 Cuando se asigna un valor `xs:time` a un objeto <xref:System.DateTime>, el campo <xref:System.DateTime.MinValue> se utiliza para inicializar las propiedades de fecha del objeto <xref:System.DateTime> (por ejemplo, <xref:System.DateTime.Year%2A>, <xref:System.DateTime.Month%2A> y <xref:System.DateTime.Day%2A>) con el valor <xref:System.DateTime> más pequeño posible.  
  
 Igualmente, las instancias de `xs:gMonth`, `xs:gDay`, `xs:gYear`, `xs:gYearMonth` y `xs:gMonthDay` también se asignan a un objeto <xref:System.DateTime>. Las propiedades no utilizadas del objeto <xref:System.DateTime> se inicializan con las de <xref:System.DateTime.MinValue>.  
  
> [!NOTE]
> No puede confiar en el valor de <xref:System.DateTime.Year%2A?displayProperty=nameWithType> si el contenido tiene el tipo `xs:gMonthDay`. El valor de <xref:System.DateTime.Year%2A?displayProperty=nameWithType> siempre está establecido en 1904 en este caso.  
  
### <a name="xsanyuri-and-systemuri"></a>xs:anyURI y System.Uri  
 Cuando se asigna una instancia de `xs:anyURI` que representa un identificador URI relativo a <xref:System.Uri>, el objeto <xref:System.Uri> no tiene un identificador URI básico.  
  
## <a name="see-also"></a>Vea también

- [Compatibilidad de tipos en las clases System.Xml](../../../../docs/standard/data/xml/type-support-in-the-system-xml-classes.md)
