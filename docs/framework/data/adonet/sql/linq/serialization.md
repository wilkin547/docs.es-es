---
title: Serialization2
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: a15ae411-8dc2-4ca3-84d2-01c9d5f1972a
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 844f206219fed527b73b5125ab82f1c044c59b5b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="serialization"></a>Serialización
Este tema se describe [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] características de la serialización. En los párrafos siguientes se proporciona información sobre cómo agregar la característica de serialización durante la generación de código en tiempo de diseño y el comportamiento de serialización en tiempo de ejecución de las clases [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].  
  
 Puede agregar código de serialización en tiempo de diseño mediante cualquiera de estos métodos:  
  
-   En el [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)], cambie la **modo de serialización** propiedad **Unidirectional**.  
  
-   En la línea de comandos SQLMetal, agregue el **/serialization** opción. Para obtener más información, vea [SqlMetal.exe (Herramienta de generación de código)](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md).  
  
## <a name="overview"></a>Información general  
 El código generado por [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] proporciona capacidades de la carga aplazada de forma predeterminada. La carga aplazada es muy apropiada en el nivel intermedio, para una carga de datos transparente a petición. Sin embargo, da problemas para la serialización, porque el serializador activa la carga aplazada esté prevista o no. De hecho, cuando se serializa un objeto, se serializa su cierre transitivo en todas las referencias con carga aplazada salientes.  
  
 El [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] característica de serialización resuelve este problema, principalmente a través de dos mecanismos:  
  
-   Un modo <xref:System.Data.Linq.DataContext> para desactivar la carga aplazada (<xref:System.Data.Linq.DataContext.ObjectTrackingEnabled%2A>). Para obtener más información, consulta <xref:System.Data.Linq.DataContext>.  
  
-   Un modificador de generación de código para generar los atributos <xref:System.Runtime.Serialization.DataContractAttribute?displayProperty=nameWithType> y <xref:System.Runtime.Serialization.DataMemberAttribute?displayProperty=nameWithType> en las entidades generadas. Este aspecto, que incluye el comportamiento de la carga aplazada de las clases en la serialización, es el asunto principal de este tema.  
  
### <a name="definitions"></a>Definiciones  
  
-   *Serializador DataContract*: serializador predeterminado utilizado por el componente de Windows Communication Framework (WCF) del .NET Framework 3.0 o versiones posteriores.  
  
-   *Serialización unidireccional*: la versión serializada de una clase que contiene sólo una propiedad de asociación unidireccional (para evitar un ciclo). Por convención, se marca para la serialización la propiedad que se encuentra en el lado primario de una relación de clave externa y clave principal. No se serializa el otro lado en una asociación bidireccional.  
  
     La serialización unidireccional es el único tipo de serialización que [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] admite.  
  
## <a name="code-example"></a>Ejemplo de código  
 El código siguiente utiliza las clases `Customer` y `Order` tradicionales de la base de datos de ejemplo Northwind y muestra cómo estas clases se decoran con atributos de serialización.  
  
 [!code-csharp[DLinqSerialization#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSerialization/cs/northwind-ser.cs#1)]
 [!code-vb[DLinqSerialization#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSerialization/vb/northwind-ser.vb#1)]  
  
 [!code-csharp[DLinqSerialization#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSerialization/cs/northwind-ser.cs#2)]
 [!code-vb[DLinqSerialization#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSerialization/vb/northwind-ser.vb#2)]  
  
 [!code-csharp[DLinqSerialization#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSerialization/cs/northwind-ser.cs#3)]
 [!code-vb[DLinqSerialization#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSerialization/vb/northwind-ser.vb#3)]  
  
 Para la clase `Order` del ejemplo siguiente, por brevedad solo se muestra la propiedad de asociación inversa que corresponde a la clase `Customer`. No tiene un atributo `DataMember` para evitar un ciclo.  
  
 [!code-csharp[DLinqSerialization#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSerialization/cs/northwind-ser.cs#4)]
 [!code-vb[DLinqSerialization#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSerialization/vb/northwind-ser.vb#4)]  
  
 [!code-csharp[DLinqSerialization#5](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSerialization/cs/northwind-ser.cs#5)]
 [!code-vb[DLinqSerialization#5](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSerialization/vb/northwind-ser.vb#5)]  
  
### <a name="how-to-serialize-the-entities"></a>Cómo serializar entidades  
 Puede serializar las entidades del código que se incluía en la sección anterior de la manera siguiente:  
  
 [!code-csharp[DLinqSerialization#6](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSerialization/cs/Program.cs#6)]
 [!code-vb[DLinqSerialization#6](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSerialization/vb/Module1.vb#6)]  
  
### <a name="self-recursive-relationships"></a>Relaciones auto-recursivas  
 Las relaciones auto-recursivas siguen el mismo patrón. La propiedad de asociación que corresponde a la clave externa no tiene un atributo `DataMember`, mientras que la propiedad primaria sí lo tiene.  
  
 Considere la clase siguiente, que tiene dos relaciones auto-recursivas: Employee.Manager/Reports y Employee.Mentor/Mentees.  
  
 [!code-csharp[DLinqSerialization#7](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSerialization/cs/northwind-ser.cs#7)]
 [!code-vb[DLinqSerialization#7](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSerialization/vb/northwind-ser.vb#7)]  
  
## <a name="see-also"></a>Vea también  
 [Información general](../../../../../../docs/framework/data/adonet/sql/linq/background-information.md)  
 [SqlMetal.exe (Herramienta de generación de código)](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md)  
 [Cómo: serializar entidades](../../../../../../docs/framework/data/adonet/sql/linq/how-to-make-entities-serializable.md)
