---
title: "Almacenamiento en cach&#233; del plan de consulta | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
ms.assetid: 90b0c685-5ef2-461b-98b4-c3c0a2b253c7
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# Almacenamiento en cach&#233; del plan de consulta
Siempre que se intenta ejecutar una consulta, la canalización de la consulta examina la memoria caché del plan de consulta para comprobar si la citada consulta ya está compilada y disponible.  En ese caso, vuelve a utilizar el plan almacenado en caché en lugar de compilar uno nuevo.  Si no se encuentra ninguna coincidencia en la memoria caché del plan de consulta, la consulta se compila y se almacena en memoria caché.  Las consultas se identifican mediante su colección de parámetros \(nombres y tipos\) y texto de [!INCLUDE[esql](../../../../../../includes/esql-md.md)].  Todas las comparaciones de texto distinguen mayúsculas de minúsculas.  
  
## Configuración  
 El almacenamiento en caché del plan de consulta se puede configurar a través del comando <xref:System.Data.EntityClient.EntityCommand>.  
  
 Para habilitar o deshabilitar el almacenamiento en caché del plan de consulta a través de la propiedad <xref:System.Data.EntityClient.EntityCommand.EnablePlanCaching%2A?displayProperty=fullName>, establezca esta propiedad en `true` o `false`, respectivamente.  Si se deshabilita el almacenamiento en caché del plan en consultas dinámicas individuales que no es probable que se usen más de una vez, mejora el rendimiento.  
  
 Puede habilitar el almacenamiento en caché del plan de consultas a través de <xref:System.Data.Objects.ObjectQuery.EnablePlanCaching%2A>.  
  
## Práctica recomendada  
 En general, se deben evitar las consultas dinámicas.  El ejemplo de consulta dinámica siguiente es vulnerable a los ataques de inyección de SQL, porque toma directamente los datos proporcionados por el usuario sin efectuar ninguna validación.  
  
 `"SELECT sp.SalesYTD FROM AdventureWorksEntities.SalesPerson as sp WHERE sp.EmployeeID = " + employeeTextBox.Text;`  
  
 Si utiliza las consultas generadas dinámicamente, considere deshabilitar el almacenamiento en memoria caché del plan de consultas para evitar el consumo de memoria innecesario para las entradas de la memoria caché que no es probable que se vuelvan a usar.  
  
 El almacenamiento en caché del plan de consulta en consultas estáticas y parametrizadas puede proporcionar mejoras en el rendimiento.  A continuación se muestra un ejemplo de consulta estática:  
  
```  
"SELECT sp.SalesYTD FROM AdventureWorksEntities.SalesPerson as sp";  
```  
  
 Para que se encuentre una coincidencia apropiada de las consultas en la memoria caché del plan de consulta, estas deben cumplir los requisitos siguientes:  
  
-   El texto de la consulta debe ser un patrón constante, preferentemente una cadena o un recurso constante.  
  
-   Se debe utilizar <xref:System.Data.EntityClient.EntityParameter> o <xref:System.Data.Objects.ObjectParameter> siempre que se deba pasar un valor proporcionado por el usuario.  
  
 Se deben evitar los patrones de consulta siguientes, que consumen innecesariamente espacios en la memoria caché del plan de consulta:  
  
-   Cambios en las mayúsculas o minúsculas del texto.  
  
-   Cambios en los espacios en blanco.  
  
-   Cambios en los valores literales.  
  
-   Cambios en el texto incluido en los comentarios.  
  
## Vea también  
 [Información general de Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)