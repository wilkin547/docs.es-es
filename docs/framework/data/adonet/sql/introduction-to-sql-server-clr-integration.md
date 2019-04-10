---
title: Introducción a la integración con CLR de SQL Server
ms.date: 03/30/2017
ms.assetid: 551d2290-ed80-49be-b377-44b32444da1c
ms.openlocfilehash: dc7d19bf361ed5fcda1fd5edf64eeb5e4ce15a71
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/09/2019
ms.locfileid: "59336816"
---
# <a name="introduction-to-sql-server-clr-integration"></a>Introducción a la integración con CLR de SQL Server
Common Language Runtime (CLR) es el núcleo de Microsoft .NET Framework y proporciona el entorno de ejecución de todo el código de .NET Framework. El código que se ejecuta en CLR se conoce como código administrado. El CLR proporciona diversas funciones y servicios necesarios para la ejecución de los programas, como compilación just-in-time (JIT), asignación y administración de memoria, aplicación de la seguridad de tipos, control de excepciones, administración de subprocesos y seguridad.  
  
 Con el CLR hospedado en Microsoft SQL Server (lo que se denomina integración con CLR), puede crear procedimientos almacenados, desencadenadores, funciones definidas por el usuario, tipos definidos por el usuario y agregados definidos por el usuario en código administrado. Como el código administrado se compila a código nativo antes de su ejecución, en algunas situaciones puede conseguir aumentos significativos del rendimiento.  
  
 El código administrado utiliza seguridad de acceso del código (CAS), vínculos a código y dominios de aplicación para impedir que los ensamblados realicen determinadas operaciones. SQL Server usa CAS para ayudar a proteger el código administrado e impedir que el sistema operativo o el servidor de bases de datos se pongan en peligro.  
  
 El objetivo de esta sección es proporcionar suficiente información para iniciarse en la programación con la integración CLR de SQL Server; no pretende tratar el tema en toda su extensión. Para obtener información más detallada, busque la versión de SQL Server que utiliza en los Libros en pantalla de SQL Server.  
  
 **Libros en pantalla de SQL Server**  
  
-   [Información general sobre integración CLR (Common Language Runtime)](https://go.microsoft.com/fwlink/?LinkId=115242)  
  
## <a name="enabling-clr-integration"></a>Habilitación de la integración con CLR  
 La característica de integración con Common Language Runtime (CLR) está desactivada de forma predeterminada en Microsoft SQL Server y se debe habilitar para utilizar los objetos que se implementan mediante la integración con CLR. Para habilitar la integración con CLR mediante Transact-SQL, utilice la opción `clr enabled` del procedimiento almacenado `sp_configure` como se muestra:  
  
```  
sp_configure 'clr enabled', 1  
GO  
RECONFIGURE  
GO  
```  
  
 Puede deshabilitar la integración con CLR estableciendo la opción `clr enabled` en 0. Cuando deshabilita esta característica, SQL Server deja de ejecutar todas las rutinas CLR y descarga todos los dominios de aplicaciones.  
  
 Para obtener información más detallada, busque la versión de SQL Server que utiliza en los Libros en pantalla de SQL Server.  
  
 **Libros en pantalla de SQL Server**  
  
-   [Habilitación de la integración con CLR](https://go.microsoft.com/fwlink/?LinkId=115230)  
  
## <a name="deploying-a-clr-assembly"></a>Implementar un ensamblado CLR  
 Una vez probados y comprobados los métodos CLR en el servidor de prueba, se pueden distribuir a los servidores de producción mediante un script de implementación, que se puede generar manualmente o con SQL Server Management Studio. Para obtener información más detallada, busque la versión de SQL Server que utiliza en los Libros en pantalla de SQL Server.  
  
 **Libros en pantalla de SQL Server**  
  
1. [Implementar objetos de base de datos de CLR](https://go.microsoft.com/fwlink/?LinkId=115232)  
  
## <a name="clr-integration-security"></a>Seguridad de la integración CLR  
 El modelo de seguridad de la integración de Microsoft SQL Server con Common Language Runtime (CLR) de Microsoft .NET Framework administra y protege el acceso entre diferentes tipos de objetos CLR y objetos que no son CLR que se ejecutan en SQL Server. Para llamar a estos objetos se puede utilizar una instrucción Transact-SQL u otro objeto CLR que se ejecute en el servidor.  
  
 Para obtener información más detallada, busque la versión de SQL Server que utiliza en los Libros en pantalla de SQL Server.  
  
 **Libros en pantalla de SQL Server**  
  
-   [Seguridad de la integración CLR](https://go.microsoft.com/fwlink/?LinkId=115234)  
  
## <a name="debugging-a-clr-assembly"></a>Depuración de un ensamblado CLR  
 Microsoft SQL Server ofrece compatibilidad con la depuración de objetos Transact-SQL y Common Language Runtime (CLR) de la base de datos. La depuración funciona entre lenguajes: los usuarios pueden entrar sin problemas en los objetos CLR desde Transact-SQL y viceversa.  
  
 Para obtener información más detallada, busque la versión de SQL Server que utiliza en los Libros en pantalla de SQL Server.  
  
 **Libros en pantalla de SQL Server**  
  
-   [Depurar objetos de bases de datos CLR](https://go.microsoft.com/fwlink/?LinkId=115236)  
  
## <a name="see-also"></a>Vea también

- [Seguridad de acceso del código y ADO.NET](../../../../../docs/framework/data/adonet/code-access-security.md)
- [Proveedores administrados de ADO.NET y centro de desarrolladores de DataSet](https://go.microsoft.com/fwlink/?LinkId=217917)
