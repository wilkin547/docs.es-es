---
description: 'Más información acerca de: requisitos del sistema para el proveedor de datos de .NET Framework para Oracle'
title: Requisitos del sistema para el proveedor de datos .NET Framework para Oracle
ms.date: 03/30/2017
ms.assetid: 054f76b9-1737-43f0-8160-84a00a387217
ms.openlocfilehash: 6b48ab695fdb87b2f51f4fe29589305325329098
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99766834"
---
# <a name="system-requirements-for-the-net-framework-data-provider-for-oracle"></a>Requisitos del sistema para el proveedor de datos .NET Framework para Oracle

El proveedor de datos .NET Framework para Oracle requiere Microsoft Data Access Components (MDAC), versión 2.6 o posterior. Se recomienda MDAC 2.8 SP1.  
  
 También debe tener instalado Oracle 8i Release 3 (8.1.7) Client o posterior.  
  
 El software Oracle Client anterior a la versión Oracle 9i no puede tener acceso a las bases de datos UTF16 dado que UTF16 es una nueva característica en Oracle 9i. Para utilizar esta característica, deberá actualizar el software de cliente a Oracle 9i o posterior.  
  
## <a name="working-with-the-data-provider-for-oracle-and-unicode-data"></a>Trabajo con el proveedor de datos para Oracle y datos Unicode  

A continuación se muestra una lista de problemas relacionados con Unicode que se deben tener en cuenta al trabajar con el proveedor de datos de .NET Framework para Oracle y las bibliotecas de cliente de Oracle. Para obtener más información, vea la documentación de Oracle.  
  
### <a name="setting-the-unicode-value-in-a-connection-string-attribute"></a>Definición de un valor Unicode en un atributo de cadena de conexión  

Al trabajar con Oracle, puede utilizar el atributo de cadena de conexión   
  
`Unicode=True`
  
para inicializar las bibliotecas de cliente de Oracle en modo UTF-16. De esta manera, las bibliotecas de cliente de Oracle aceptarán UTF-16 (que es muy parecido a UCS-2) en lugar de cadenas de varios bytes. Como consecuencia, el proveedor de datos para Oracle puede trabajar siempre con cualquier página de códigos Oracle sin necesidad de trabajo de conversión adicional. Esta configuración sólo funciona si utiliza clientes Oracle 9i para comunicarse con una base de datos Oracle 9i con el juego de caracteres alternativo de AL16UTF16. Cuando un cliente de Oracle 9i se comunica con un servidor Oracle 9i, se necesitan recursos adicionales para convertir los valores **CommandText** de Unicode al Juego de caracteres de varios bytes adecuado que usa el servidor Oracle9i. Esto se puede evitar si sabe que tiene la configuración segura agregando `Unicode=True` a la cadena de conexión.  
  
### <a name="mixing-versions-of-oracle-client-and-oracle-server"></a>Mezcla de versiones de Oracle Client y Oracle Server  

Los clientes de Oracle 8i no pueden tener acceso a los datos **nchar**, **NVARCHAR2** o **NCLOB** en las bases de datos de Oracle 9i cuando el juego de caracteres nacional del servidor se especifica como AL16UTF16 (el valor predeterminado para Oracle 9i). Como hasta Oracle 9i no se introdujo la compatibilidad con el juego de caracteres UTF-16, los clientes Oracle 8i no pueden leerlo.  
  
### <a name="working-with-utf-8-data"></a>Trabajo con datos UTF-8  

Para definir el juego de caracteres alternativo, establezca la clave del Registro HKEY_LOCAL_MACHINE\SOFTWARE\ORACLE\HOMEID\NLS_LANG en UTF8. Para obtener más información, vea las notas de instalación de Oracle correspondientes a su plataforma. La opción predeterminada es el juego de caracteres principal del idioma con el que va a instalar el software Oracle Client. Si no establece el idioma para que coincida con el juego de caracteres del idioma nacional de la base de datos a la que se va a conectar, ocasionará que los enlaces de parámetros y columnas envíen o reciban datos con el juego de caracteres principal de la base de datos, y no con el juego de caracteres nacional.  
  
### <a name="oraclelob-can-only-update-full-characters"></a>OracleLob sólo puede actualizar caracteres completos.  

Por motivos de facilidad de uso, el <xref:System.Data.OracleClient.OracleLob> objeto hereda de la clase .NET Framework Stream y proporciona los métodos **ReadByte** y **WriteByte** . También implementa métodos, como **CopyTo** y **Erase**, que funcionan en secciones de objetos **LOB** de Oracle. Por el contrario, el software cliente de Oracle proporciona una serie de API para trabajar con los caracteres **LOB**(**CLOB** y **NCLOB**). No obstante, estas API sólo funcionan en caracteres completos. Debido a esta diferencia, el proveedor de datos para Oracle implementa la compatibilidad con **Read** y **ReadByte** para trabajar con datos UTF-16 de forma de byte. Sin embargo, los otros métodos del objeto **OracleLob** solo permiten operaciones de caracteres completos.  
  
## <a name="see-also"></a>Vea también

- [Oracle y ADO.NET](oracle-and-adonet.md)
- [Información general de ADO.NET](ado-net-overview.md)
