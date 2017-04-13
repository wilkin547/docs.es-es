---
title: "N&#250;meros en punto flotante | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 73c218c6-1c44-4402-a167-4f6262629a91
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# N&#250;meros en punto flotante
En este tema se describen algunos de los problemas que con frecuencia se encuentran los programadores al trabajar con números de punto flotante en [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)].  Estos problemas se deben a la forma en que los equipos almacenan los números de punto flotante y no son específicos de ningún proveedor determinado, como <xref:System.Data.SqlClient> o <xref:System.Data.OracleClient>.  
  
 En general, los números de punto flotante no tienen una representación binaria exacta.  En realidad, el equipo almacena una aproximación del número.  En diferentes momentos se pueden utilizar diferentes números de dígitos binarios para representar el número.  Cuando un número de punto flotante se convierte de una representación a otra, los dígitos menos significativos de dicho número pueden variar ligeramente.  Por lo general el cambio se produce cuando el número se convierte de un tipo a otro.  La variación se produce si la conversión se realiza en una base de datos, entre tipos que representan valores de base de datos o entre tipos.  Debido a estos cambios, los números que lógicamente deberían ser iguales pueden presentar cambios en sus dígitos menos significativos que hagan que muestren valores diferentes.  La cantidad de dígitos de precisión en el número puede ser mayor o menor de la esperada.  Cuando el formato del número cambia a cadena, puede que no muestre el valor esperado.  
  
 Para reducir estos efectos al mínimo, debe usar la coincidencia más próxima entre tipos de números que haya disponible.  Por ejemplo, si trabaja con [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)], el valor numérico exacto puede cambiar si convierte un valor de tipo real de Transact\-SQL a un valor de tipo flotante.  En [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)], la conversión de <xref:System.Single> a <xref:System.Double> también puede producir resultados inesperados.  En ambos casos, una estrategia adecuada consiste en establecer que todos los valores de la aplicación usen el mismo tipo numérico.  También puede utilizar un tipo de decimal de precisión fija o bien convertir los números de punto flotante a un tipo decimal de precisión fija antes de trabajar con ellos.  
  
 Para solucionar problemas relacionados con la comparación de igualdad, puede codificar la aplicación de forma que se pasen por alto las diferentes en los dígitos menos significativos.  Por ejemplo, en lugar de comparar dos números para comprobar si son iguales, puede restar un número del otro.  Si la diferencia se sitúa en un margen aceptable de redondeo, la aplicación puede considerar los números como si fuesen iguales.  
  
## Vea también  
 [Por qué los números de punto flotante pierden precisión](../Topic/Why%20Floating-Point%20Numbers%20May%20Lose%20Precision.md)   
 [Proveedores administrados de ADO.NET y centro de desarrolladores de conjuntos de datos](http://go.microsoft.com/fwlink/?LinkId=217917)