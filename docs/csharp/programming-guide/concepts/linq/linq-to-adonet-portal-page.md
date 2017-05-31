---
title: "LINQ to ADO.NET (Página de portal) | Microsoft Docs"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: 6bd269b4-3509-4688-b672-836008704182
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Human Translation
ms.sourcegitcommit: fe32676f0e39ed109a68f39584cf41aec5f5ce90
ms.openlocfilehash: 34ffcb1c75daa403388b8708dc7abb0e8c1a370e
ms.contentlocale: es-es
ms.lasthandoff: 05/10/2017

---
# <a name="linq-to-adonet-portal-page"></a>LINQ to ADO.NET (Página de portal)
[!INCLUDE[linq_adonet](../../../../csharp/programming-guide/concepts/linq/includes/linq_adonet_md.md)] permite consultar sobre cualquier objeto enumerable de [!INCLUDE[vstecado](../../../../csharp/programming-guide/concepts/linq/includes/vstecado_md.md)] mediante el modelo de programación de [!INCLUDE[vbteclinqext](../../../../csharp/getting-started/includes/vbteclinqext_md.md)].  
  
> [!NOTE]
>  La documentación de [!INCLUDE[linq_adonet](../../../../csharp/programming-guide/concepts/linq/includes/linq_adonet_md.md)] se encuentra en la sección ADO.NET del SDK de .NET Framework: [LINQ y ADO.NET](http://msdn.microsoft.com/library/bf0c8f93-3ff7-49f3-8aed-f2b7ac938dec).  
  
 Existen tres tecnologías [!INCLUDE[vbteclinqext](../../../../csharp/getting-started/includes/vbteclinqext_md.md)] de ADO.NET independientes: [!INCLUDE[linq_dataset](../../../../csharp/programming-guide/concepts/linq/includes/linq_dataset_md.md)], [!INCLUDE[vbtecdlinq](../../../../csharp/includes/vbtecdlinq_md.md)] y [!INCLUDE[linq_entities](../../../../csharp/programming-guide/concepts/linq/includes/linq_entities_md.md)]. [!INCLUDE[linq_dataset](../../../../csharp/programming-guide/concepts/linq/includes/linq_dataset_md.md)] proporciona consultas más ricas y optimizadas de <xref:System.Data.DataSet>, [!INCLUDE[vbtecdlinq](../../../../csharp/includes/vbtecdlinq_md.md)] permite consultar directamente los esquemas de base de datos de [!INCLUDE[ssNoVersion](../../../../csharp/programming-guide/concepts/linq/includes/ssnoversion_md.md)] y [!INCLUDE[linq_entities](../../../../csharp/programming-guide/concepts/linq/includes/linq_entities_md.md)] permite consultar un [!INCLUDE[adonet_edm](../../../../csharp/programming-guide/concepts/linq/includes/adonet_edm_md.md)].  
  
## <a name="linq-to-dataset"></a>LINQ to DataSet  
 <xref:System.Data.DataSet> es uno de los componentes más usados de [!INCLUDE[vstecado](../../../../csharp/programming-guide/concepts/linq/includes/vstecado_md.md)], además de un elemento clave del modelo de programación desconectado en el que se basa [!INCLUDE[vstecado](../../../../csharp/programming-guide/concepts/linq/includes/vstecado_md.md)]. En cambio, a pesar de su importancia, <xref:System.Data.DataSet> tiene funciones de consulta limitadas.  
  
 [!INCLUDE[linq_dataset](../../../../csharp/programming-guide/concepts/linq/includes/linq_dataset_md.md)] le permite compilar funciones de consulta más complejas en <xref:System.Data.DataSet> mediante la misma función de consulta disponible para muchos otros orígenes de datos.  
  
 Para más información, vea [LINQ to DataSet](../../../../framework/data/adonet/linq-to-dataset.md).  
  
## <a name="linq-to-sql"></a>LINQ to SQL  
 [!INCLUDE[vbtecdlinq](../../../../csharp/includes/vbtecdlinq_md.md)] proporciona una infraestructura en tiempo de ejecución para administrar los datos relacionales como objetos. En [!INCLUDE[vbtecdlinq](../../../../csharp/includes/vbtecdlinq_md.md)], el modelo de datos de una base de datos relacional se asigna a un modelo de objetos expresado en el lenguaje de programación del desarrollador. Cuando se ejecuta la aplicación, [!INCLUDE[vbtecdlinq](../../../../csharp/includes/vbtecdlinq_md.md)] convierte a SQL las consultas integradas en el lenguaje en el modelo de objetos y las envía a la base de datos para su ejecución. Cuando la base de datos devuelve los resultados, [!INCLUDE[vbtecdlinq](../../../../csharp/includes/vbtecdlinq_md.md)] los vuelve a convertir en objetos que se pueden manipular.  
  
 [!INCLUDE[vbtecdlinq](../../../../csharp/includes/vbtecdlinq_md.md)] incluye compatibilidad con los procedimientos almacenados y las funciones definidas por el usuario de la base de datos, además de con la herencia en el modelo de objetos.  
  
 Para más información, vea [LINQ to SQL](https://msdn.microsoft.com/library/bb386976).  
  
## <a name="linq-to-entities"></a>LINQ to Entities  
 A través de [!INCLUDE[adonet_edm](../../../../csharp/programming-guide/concepts/linq/includes/adonet_edm_md.md)], los datos relacionales se exponen como objetos en el entorno .NET. Esto hace de la capa de objetos un objetivo idóneo para la compatibilidad con [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)], ya que permite a los programadores formular consultas en la base de datos con el lenguaje usado para compilar la lógica empresarial. Esta función se conoce como [!INCLUDE[linq_entities](../../../../csharp/programming-guide/concepts/linq/includes/linq_entities_md.md)]. Para más información, vea [LINQ to Entities](../../../../framework/data/adonet/ef/language-reference/linq-to-entities.md).  
  
## <a name="see-also"></a>Vea también  
 [LINQ y ADO.NET](http://msdn.microsoft.com/library/bf0c8f93-3ff7-49f3-8aed-f2b7ac938dec)   
 [Language Integrated Query (LINQ) (C#)](../../../../csharp/programming-guide/concepts/linq/index.md)
