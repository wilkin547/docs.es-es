---
title: "Requisitos del sistema para el proveedor de datos .NET Framework para Oracle | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 054f76b9-1737-43f0-8160-84a00a387217
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# Requisitos del sistema para el proveedor de datos .NET Framework para Oracle
El proveedor de datos .NET Framework para Oracle requiere Microsoft Data Access Components \(MDAC\), versión 2.6 o posterior.  Se recomienda MDAC 2.8 SP1.  
  
 También debe tener instalado Oracle 8i Release 3 \(8.1.7\) Client o posterior.  
  
 El software Oracle Client anterior a la versión Oracle 9i no puede tener acceso a las bases de datos UTF16 dado que UTF16 es una nueva característica en Oracle 9i.  Para utilizar esta característica, deberá actualizar el software de cliente a Oracle 9i o posterior.  
  
## Trabajo con el proveedor de datos para Oracle y datos Unicode  
 A continuación se muestra una lista de problemas relacionados con Unicode que se deben tener en cuenta a la hora de trabajar con el proveedor de datos .NET Framework para Oracle y bibliotecas de cliente de Oracle.  Para obtener más información, vea la documentación de Oracle.  
  
### Definición de un valor Unicode en un atributo de cadena de conexión  
 Al trabajar con Oracle, puede utilizar el atributo de cadena de conexión  
  
```  
Unicode=True   
```  
  
 para inicializar las bibliotecas de cliente de Oracle en modo UTF\-16.  De esta manera, las bibliotecas de cliente de Oracle aceptarán UTF\-16 \(que es muy parecido a UCS\-2\) en lugar de cadenas de varios bytes.  Como consecuencia, el proveedor de datos para Oracle puede trabajar siempre con cualquier página de códigos Oracle sin necesidad de trabajo de conversión adicional.  Esta configuración sólo funciona si utiliza clientes Oracle 9i para comunicarse con una base de datos Oracle 9i con el juego de caracteres alternativo de AL16UTF16.  Cuando un cliente Oracle 9i se comunica con un servidor Oracle 9i, se necesitan recursos adicionales para convertir los valores **CommandText** de Unicode al juego de caracteres de varios bytes adecuado que utiliza el servidor Oracle9i.  Esto se puede evitar si sabe que tiene la configuración segura agregando `Unicode=True` a la cadena de conexión.  
  
### Mezcla de versiones de Oracle Client y Oracle Server  
 Los clientes Oracle 8i no pueden tener acceso a datos **NCHAR**, **NVARCHAR2** o **NCLOB** en bases de datos Oracle 9i cuando el juego de caracteres nacional del servidor se especifica como AL16UTF16 \(el valor predeterminado en Oracle 9i\).  Como hasta Oracle 9i no se introdujo la compatibilidad con el juego de caracteres UTF\-16, los clientes Oracle 8i no pueden leerlo.  
  
### Trabajo con datos UTF\-8  
 Para definir el juego de caracteres alternativo, establezca la clave del Registro HKEY\_LOCAL\_MACHINE\\SOFTWARE\\ORACLE\\HOMEID\\NLS\_LANG en UTF8.  Para obtener más información, vea las notas de instalación de Oracle correspondientes a su plataforma.  La opción predeterminada es el juego de caracteres principal del idioma con el que va a instalar el software Oracle Client.  Si no establece el idioma para que coincida con el juego de caracteres del idioma nacional de la base de datos a la que se va a conectar, ocasionará que los enlaces de parámetros y columnas envíen o reciban datos con el juego de caracteres principal de la base de datos, y no con el juego de caracteres nacional.  
  
### OracleLob sólo puede actualizar caracteres completos.  
 Por motivos de capacidad de uso, el objeto <xref:System.Data.OracleClient.OracleLob> se hereda de la clase Stream de .NET Framework y proporciona los métodos **ReadByte** y **WriteByte**.  También implementa métodos, como **CopyTo** y **Erase**, que funcionan en secciones de objetos Oracle **LOB**.  Por el contrario, el software de cliente Oracle proporciona varias API que funcionan con caracteres **LOB** \(**CLOB** y **NCLOB**\).  No obstante, estas API sólo funcionan en caracteres completos.  Debido a esta diferencia, el proveedor de datos para Oracle implementa compatibilidad con **Read** y **ReadByte** para trabajar con datos UTF\-16 de forma que se tenga en cuenta el número de bytes.  Sin embargo, los demás métodos del objeto **OracleLob** sólo permiten operaciones de caracteres completos.  
  
## Vea también  
 [Oracle y ADO.NET](../../../../docs/framework/data/adonet/oracle-and-adonet.md)   
 [Proveedores administrados de ADO.NET y centro de desarrolladores de conjuntos de datos](http://go.microsoft.com/fwlink/?LinkId=217917)