---
title: "Escribir un proveedor de datos de Entity Framework | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 092e88c4-a301-453a-b5c3-5740c6575a9f
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# Escribir un proveedor de datos de Entity Framework
Esta sección explica cómo escribir un proveedor de [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] para admitir un origen de datos distinto de [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)].  [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] incluye un proveedor que admite [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)].  
  
## Introducción al modelo de proveedor de Entity Framework  
 [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] es independiente de la base de datos, por lo que puede escribir un proveedor utilizando el modelo de proveedor de ADO.NET para conectar a un conjunto diverso de orígenes de datos.  
  
 El proveedor de datos de Entity Framework \(compilado mediante el modelo de proveedor de datos de ADO.NET\) realiza las siguientes funciones:  
  
-   Asigna los tipos primitivos de Entity Data Model \(EDM\) a los tipos de proveedor.  
  
-   Expone funciones específicas del proveedor.  
  
-   Genera comandos específicos del proveedor para que un elemento DbQueryCommandTree determinado admita consultas de [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].  
  
-   Genera comandos de actualización específicos del proveedor para que un elemento DbModificationCommandTree determinado admita las actualizaciones a través de [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].  
  
-   Expone archivos de asignación para la definición de esquema de almacenamiento, para admitir la generación de un modelo basado en una base de datos.  
  
-   Expone metadatos \(tablas y vistas, por ejemplo\) a través de un modelo conceptual.  
  
 ![b42a7a5c&#45;0ac0&#45;4911&#45;86be&#45;0460a78760ba](../../../../../docs/framework/data/adonet/ef/media/b42a7a5c-0ac0-4911-86be-0460a78760ba.gif "b42a7a5c\-0ac0\-4911\-86be\-0460a78760ba")  
  
## Ejemplo  
 Vaya al [proveedor de ejemplo de Entity Framework](http://go.microsoft.com/fwlink/?LinkId=180616) para ver un ejemplo de un proveedor de [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] que admite un origen de datos distinto a [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)].  
  
## En esta sección  
 [Generación de SQL](../../../../../docs/framework/data/adonet/ef/sql-generation.md)  
  
 [Generar SQL de modificación](../../../../../docs/framework/data/adonet/ef/modification-sql-generation.md)  
  
 [Especificación del manifiesto del proveedor](../../../../../docs/framework/data/adonet/ef/provider-manifest-specification.md)  
  
## Vea también  
 [Trabajar con proveedores de datos](../../../../../docs/framework/data/adonet/ef/working-with-data-providers.md)