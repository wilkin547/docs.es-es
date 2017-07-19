---
title: "Serializaci&#243;n | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: a15ae411-8dc2-4ca3-84d2-01c9d5f1972a
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# Serializaci&#243;n
En este tema se describe la funcionalidad de serialización de [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].  En los párrafos siguientes se proporciona información sobre cómo agregar la característica de serialización durante la generación de código en tiempo de diseño y el comportamiento de serialización en tiempo de ejecución de las clases [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].  
  
 Puede agregar código de serialización en tiempo de diseño mediante cualquiera de estos métodos:  
  
-   En el [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)], cambie la propiedad **Modo de serialización** a **Unidirectional**.  
  
-   En la línea de comandos de SQLMetal, agregue la opción **\/serialization**.  Para obtener más información, consulte [SqlMetal.exe \(Herramienta de generación de código\)](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md).  
  
## Información general  
 El código generado por [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] proporciona funcionalidad de carga aplazada de forma predeterminada.  La carga aplazada es muy apropiada en el nivel intermedio, para una carga de datos transparente a petición.  Sin embargo, da problemas para la serialización, porque el serializador activa la carga aplazada esté prevista o no.  De hecho, cuando se serializa un objeto, se serializa su cierre transitivo en todas las referencias con carga aplazada salientes.  
  
 La característica de serialización de [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] resuelve este problema, principalmente a través de dos mecanismos:  
  
-   Un modo <xref:System.Data.Linq.DataContext> para desactivar la carga aplazada \(<xref:System.Data.Linq.DataContext.ObjectTrackingEnabled%2A>\).  Para obtener más información, consulta <xref:System.Data.Linq.DataContext>.  
  
-   Un modificador de generación de código para generar los atributos <xref:System.Runtime.Serialization.DataContractAttribute?displayProperty=fullName> y <xref:System.Runtime.Serialization.DataMemberAttribute?displayProperty=fullName> en las entidades generadas.  Este aspecto, que incluye el comportamiento de la carga aplazada de las clases en la serialización, es el asunto principal de este tema.  
  
### Definiciones  
  
-   *Serializador DataContract*: serializador predeterminado utilizado por el componente WCF de .NET Framework 3.0 o versiones posteriores.  
  
-   *Serialización unidireccional*: versión serializada de una clase que contiene solo una propiedad de asociación unidireccional \(para evitar un ciclo\).  Por convención, se marca para la serialización la propiedad que se encuentra en el lado primario de una relación de clave externa y clave principal.  No se serializa el otro lado en una asociación bidireccional.  
  
     La serialización unidireccional es el único tipo de serialización que [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] admite.  
  
## Ejemplo de código  
 El código siguiente utiliza las clases `Customer` y `Order` tradicionales de la base de datos de ejemplo Northwind y muestra cómo estas clases se decoran con atributos de serialización.  
  
 [!code-csharp[DLinqSerialization#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSerialization/cs/northwind-ser.cs#1)]
 [!code-vb[DLinqSerialization#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSerialization/vb/northwind-ser.vb#1)]  
  
 [!code-csharp[DLinqSerialization#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSerialization/cs/northwind-ser.cs#2)]
 [!code-vb[DLinqSerialization#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSerialization/vb/northwind-ser.vb#2)]  
  
 [!code-csharp[DLinqSerialization#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSerialization/cs/northwind-ser.cs#3)]
 [!code-vb[DLinqSerialization#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSerialization/vb/northwind-ser.vb#3)]  
  
 Para la clase `Order` del ejemplo siguiente, por brevedad solo se muestra la propiedad de asociación inversa que corresponde a la clase `Customer`.  No tiene un atributo `DataMember` para evitar un ciclo.  
  
 [!code-csharp[DLinqSerialization#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSerialization/cs/northwind-ser.cs#4)]
 [!code-vb[DLinqSerialization#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSerialization/vb/northwind-ser.vb#4)]  
  
 [!code-csharp[DLinqSerialization#5](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSerialization/cs/northwind-ser.cs#5)]
 [!code-vb[DLinqSerialization#5](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSerialization/vb/northwind-ser.vb#5)]  
  
### Cómo serializar entidades  
 Puede serializar las entidades del código que se incluía en la sección anterior de la manera siguiente:  
  
 [!code-csharp[DLinqSerialization#6](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSerialization/cs/Program.cs#6)]
 [!code-vb[DLinqSerialization#6](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSerialization/vb/Module1.vb#6)]  
  
### Relaciones auto\-recursivas  
 Las relaciones auto\-recursivas siguen el mismo patrón.  La propiedad de asociación que corresponde a la clave externa no tiene un atributo `DataMember`, mientras que la propiedad primaria sí lo tiene.  
  
 Considere la clase siguiente, que tiene dos relaciones auto\-recursivas: Employee.Manager\/Reports y Employee.Mentor\/Mentees.  
  
 [!code-csharp[DLinqSerialization#7](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSerialization/cs/northwind-ser.cs#7)]
 [!code-vb[DLinqSerialization#7](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSerialization/vb/northwind-ser.vb#7)]  
  
## Vea también  
 [Información general](../../../../../../docs/framework/data/adonet/sql/linq/background-information.md)   
 [SqlMetal.exe \(Herramienta de generación de código\)](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md)   
 [Cómo: Convertir entidades en serializables](../../../../../../docs/framework/data/adonet/sql/linq/how-to-make-entities-serializable.md)