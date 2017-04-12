---
title: "LINQ to ADO.NET (Portal de página) | Documentos de Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: bbbd7c76-2981-4b91-b8d2-437547181f52
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 5c71b304dbff960320b1a9f46e38259705b8dadc
ms.lasthandoff: 03/13/2017

---
# <a name="linq-to-adonet-portal-page"></a>LINQ to ADO.NET (Página de portal)
[!INCLUDE[linq_adonet](../../../../csharp/programming-guide/concepts/linq/includes/linq_adonet_md.md)]le permite consultar cualquier objeto enumerable en [!INCLUDE[vstecado](../../../../csharp/programming-guide/concepts/linq/includes/vstecado_md.md)] utilizando el [!INCLUDE[vbteclinqext](../../../../csharp/getting-started/includes/vbteclinqext_md.md)] modelo de programación.  
  
> [!NOTE]
>  El [!INCLUDE[linq_adonet](../../../../csharp/programming-guide/concepts/linq/includes/linq_adonet_md.md)] documentación se encuentra en la sección ADO.NET de .NET Framework SDK: [LINQ y ADO.NET](http://msdn.microsoft.com/library/bf0c8f93-3ff7-49f3-8aed-f2b7ac938dec).  
  
 Existen tres tecnologías [!INCLUDE[vbteclinqext](../../../../csharp/getting-started/includes/vbteclinqext_md.md)] de ADO.NET independientes: [!INCLUDE[linq_dataset](../../../../csharp/programming-guide/concepts/linq/includes/linq_dataset_md.md)], [!INCLUDE[vbtecdlinq](../../../../csharp/includes/vbtecdlinq_md.md)] y [!INCLUDE[linq_entities](../../../../csharp/programming-guide/concepts/linq/includes/linq_entities_md.md)]. [!INCLUDE[linq_dataset](../../../../csharp/programming-guide/concepts/linq/includes/linq_dataset_md.md)]Proporciona consultas más enriquecidas y optimizadas en el <xref:System.Data.DataSet>, [!INCLUDE[vbtecdlinq](../../../../csharp/includes/vbtecdlinq_md.md)] le permite consultar directamente [!INCLUDE[ssNoVersion](../../../../csharp/programming-guide/concepts/linq/includes/ssnoversion_md.md)] esquemas, la base de datos y [!INCLUDE[linq_entities](../../../../csharp/programming-guide/concepts/linq/includes/linq_entities_md.md)] permite consultar un [!INCLUDE[adonet_edm](../../../../csharp/programming-guide/concepts/linq/includes/adonet_edm_md.md)].</xref:System.Data.DataSet>  
  
## <a name="linq-to-dataset"></a>LINQ to DataSet  
 El <xref:System.Data.DataSet>es uno de los componentes más ampliamente utilizados en [!INCLUDE[vstecado](../../../../csharp/programming-guide/concepts/linq/includes/vstecado_md.md)], y es un elemento clave de programación desconectada modelo que [!INCLUDE[vstecado](../../../../csharp/programming-guide/concepts/linq/includes/vstecado_md.md)] se basa en.</xref:System.Data.DataSet> A pesar de esta importancia, sin embargo, el <xref:System.Data.DataSet>tiene capacidades de consulta limitadas.</xref:System.Data.DataSet>  
  
 [!INCLUDE[linq_dataset](../../../../csharp/programming-guide/concepts/linq/includes/linq_dataset_md.md)]le permite crear capacidades de consulta más complejas en <xref:System.Data.DataSet>utilizando la misma funcionalidad de consulta que está disponible para muchos otros orígenes de datos.</xref:System.Data.DataSet>  
  
 Para obtener más información, consulte [LINQ to DataSet](http://msdn.microsoft.com/library/743e3755-3ecb-45a2-8d9b-9ed41f0dcf17).  
  
## <a name="linq-to-sql"></a>LINQ to SQL  
 [!INCLUDE[vbtecdlinq](../../../../csharp/includes/vbtecdlinq_md.md)] proporciona una infraestructura en tiempo de ejecución para administrar los datos relacionales como objetos. En [!INCLUDE[vbtecdlinq](../../../../csharp/includes/vbtecdlinq_md.md)], el modelo de datos de una base de datos relacional se asigna a un modelo de objeto expresado en el lenguaje de programación del desarrollador. Al ejecutar la aplicación [!INCLUDE[vbtecdlinq](../../../../csharp/includes/vbtecdlinq_md.md)] convierte las consultas integradas en el lenguaje del modelo de objetos a SQL y las envía a la base de datos para su ejecución. Cuando la base de datos devuelve los resultados, [!INCLUDE[vbtecdlinq](../../../../csharp/includes/vbtecdlinq_md.md)] traduce en objetos que se pueden manipular.  
  
 [!INCLUDE[vbtecdlinq](../../../../csharp/includes/vbtecdlinq_md.md)]incluye compatibilidad con los procedimientos almacenados y funciones definidas por el usuario en la base de datos y para la herencia en el modelo de objetos.  
  
 Para obtener más información, consulte [LINQ to SQL](https://msdn.microsoft.com/library/bb386976).  
  
## <a name="linq-to-entities"></a>LINQ to Entities  
 A través de [!INCLUDE[adonet_edm](../../../../csharp/programming-guide/concepts/linq/includes/adonet_edm_md.md)], los datos relacionales se exponen como objetos en el entorno .NET. Esto hace de la capa de objetos un objetivo idóneo para la compatibilidad con [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)], ya que permite a los programadores formular consultas en la base de datos con el lenguaje usado para compilar la lógica empresarial. Esta función se conoce como [!INCLUDE[linq_entities](../../../../csharp/programming-guide/concepts/linq/includes/linq_entities_md.md)]. Consulte [LINQ to Entities](http://msdn.microsoft.com/library/641f9b68-9046-47a1-abb0-1c8eaeda0e2d) para obtener más información.  
  
## <a name="see-also"></a>Vea también  
 [LINQ y ADO.NET](http://msdn.microsoft.com/library/bf0c8f93-3ff7-49f3-8aed-f2b7ac938dec)   
 [Language-Integrated Query (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/index.md)
