---
title: "C&#243;mo: Asignar jerarqu&#237;as de herencia | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: b27c779b-9355-4dc7-b95f-7dfd504b6e48
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# C&#243;mo: Asignar jerarqu&#237;as de herencia
Para implementar la asignación de herencia en [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)], debe especificar los atributos y las propiedades de atributo en la clase raíz de la jerarquía de herencia, tal como se describe en los pasos siguientes.  Los desarrolladores de [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] pueden utilizar el [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] para asignar jerarquías de herencia.  Consulte [Cómo: Configurar herencia usando Object Relational Designer](../Topic/How%20to:%20Configure%20inheritance%20by%20using%20the%20O-R%20Designer.md).  
  
> [!NOTE]
>  No se requieren atributos o propiedades especiales en las subclases.  Observe sobre todo que las subclases no tienen el atributo <xref:System.Data.Linq.Mapping.TableAttribute>.  
  
### Para asignar una jerarquía de herencia  
  
1.  Agregue el atributo <xref:System.Data.Linq.Mapping.TableAttribute> a la clase raíz.  
  
2.  También en la clase raíz, agregue un atributo <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute> para cada clase de la estructura jerárquica.  
  
3.  Para cada atributo <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute>, defina una propiedad <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute.Code%2A>.  
  
     Esta propiedad contiene un valor que aparece en la tabla de base de datos, en la columna <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDiscriminator%2A>, para indicar a qué clase o subclase pertenece esta fila de datos.  
  
4.  Para cada atributo <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute>, agregue también una propiedad <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute.Type%2A>.  
  
     Esta propiedad contiene un valor que especifica a qué clase o subclases representa el valor de clave.  
  
5.  En uno de los atributos <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute>, agregue una propiedad <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute.IsDefault%2A>.  
  
     Esta propiedad sirve para designar una asignación de *reserva* cuando el valor de discriminador de la tabla de base de datos no coincide con ningún valor <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute.Code%2A> de las asignaciones de herencia.  
  
6.  Agregue una propiedad <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDiscriminator%2A> para un atributo <xref:System.Data.Linq.Mapping.ColumnAttribute>.  
  
     Esta propiedad indica que ésta es la columna que contiene el valor <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute.Code%2A>.  
  
## Ejemplo  
  
> [!NOTE]
>  Si utiliza [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)], puede usar el [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] para configurar la herencia.  Consulte [Cómo: Configurar herencia usando Object Relational Designer](../Topic/How%20to:%20Configure%20inheritance%20by%20using%20the%20O-R%20Designer.md)  
  
 En el ejemplo de código siguiente, `Vehicle` se define como la clase raíz y se han implementado los pasos anteriores para describir la jerarquía para [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)].  
  
 [!code-csharp[DLinqCustomize#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCustomize/cs/Program.cs#4)]
 [!code-vb[DLinqCustomize#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCustomize/vb/Module1.vb#4)]  
  
## Vea también  
 [Compatibilidad de la herencia](../../../../../../docs/framework/data/adonet/sql/linq/inheritance-support.md)   
 [Cómo: Personalizar clases de entidad mediante el editor de código](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md)