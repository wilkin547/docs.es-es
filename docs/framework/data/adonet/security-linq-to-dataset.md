---
title: "Seguridad (LINQ to DataSet) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 6116b2b8-75f4-4d8b-aea6-c13e55cda50b
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# Seguridad (LINQ to DataSet)
En este tema se tratan temas de seguridad en [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)].  
  
## Pasar una consulta a un componente que no sea de confianza  
 Una consulta [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] se puede formular en un punto de un programa y ejecutarse en otro diferente.  En el momento en que se formula la consulta, ésta puede hacer referencia a cualquier elemento visible en ese momento, como miembros privados de la clase a la que pertenece el método de llamada o símbolos que representan variables o argumentos locales.  En tiempo de ejecución, la consulta podrá obtener acceso a los miembros a los que la consulta hizo referencia durante la formulación, incluso si el código de llamada no puede verlos.  Al código que ejecuta la consulta no se le ha agregado visibilidad de manera arbitraria por lo que no puede elegir a qué miembro debe obtener acceso.  Sólo podrá obtener acceso a lo que la consulta obtenga acceso y sólo a través de la misma consulta.  
  
 Esto implica que, al pasar una referencia a una consulta realizada a otra parte del código, el componente que recibe la consulta tiene acceso a todos los miembros públicos y privados a los que hace referencia la consulta.  En general, las consultas [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] no se deben pasar a componentes que no sean de confianza a menos que la consulta se haya construido cuidadosamente para que no muestre la información que debe ser privada.  
  
## Entrada externa  
 A menudo, las aplicaciones obtienen entradas externas \(de un usuario o de otro agente externo\) y realizan acciones basadas en dicha entrada.  En el caso de [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)], es posible que la aplicación construya una consulta de determinada manera en función de la entrada externa o utilice dicha entrada en la consulta. Las consultas [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] aceptan parámetros siempre que se acepten literales.  Los desarrolladores de aplicaciones deben utilizar consultas parametrizadas en lugar de insertar literales en la consulta procedentes de un agente externo.  
  
 Cualquier entrada derivada directa o indirectamente del usuario o de un agente externo puede inyectar contenido que aproveche la sintaxis del lenguaje de destino para realizar acciones no autorizadas.  Esto se conoce como ataque de inyección de SQL porque en el patrón de ataque el idioma de destino es Transact\-SQL.  La entrada de usuario inyectada directamente en la consulta se utiliza para quitar una tabla de base de datos, provocar un ataque de denegación de servicio o cambiar la naturaleza de la operación que se está realizando.  Aunque la composición de consultas es posible en [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)], ésta se realiza a través de la API del modelo de objetos. Las consultas [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] no se construyen manipulando ni concatenando cadenas como ocurre en Transact\-SQL y no son susceptibles de ataques de inyección de SQL en el sentido tradicional.  
  
## Vea también  
 [Guía de programación](../../../../docs/framework/data/adonet/programming-guide-linq-to-dataset.md)