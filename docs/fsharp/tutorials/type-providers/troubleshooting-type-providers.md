---
title: Solución de problemas en proveedores de tipos
description: 'Detectar posibles soluciones para los problemas que es más probable que encuentre cuando se usan proveedores de tipos en F #.'
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: e7374a051ca63e003288702c6d882e72d77d71e8
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2018
---
# <a name="troubleshooting-type-providers"></a>Solución de problemas en proveedores de tipos

Este tema describe y proporciona soluciones posibles para los problemas que es más probable que encuentre cuando utiliza proveedores de tipo.


## <a name="possible-problems-with-type-providers"></a>Posibles problemas con los proveedores de tipo
Si se produce un problema cuando se trabaja con proveedores de tipos, puede revisar la siguiente tabla para las soluciones más comunes.



|Problema|Acciones sugeridas|
|-------|-----------------|
|**Cambios de esquema**. Escriba proveedores funcionan mejor cuando el esquema de origen de datos es estable. Si agrega una tabla de datos o una columna o realizar otro cambio en ese esquema, el proveedor de tipos no reconoce automáticamente estos cambios.|Limpiar o recompilar el proyecto. Para limpiar el proyecto, elija **generar**, **limpiar** *ProjectName* en la barra de menús. Para volver a crear el proyecto, elija **generar**, **volver a generar** *ProjectName* en la barra de menús. Estas acciones restablecer todos los Estados del proveedor de tipo y forzar al proveedor para volver a conectarse al origen de datos y obtener información de esquema actualizado.|
|**Error de conexión**. La cadena de conexión o la dirección URL es correcta, la red no está funcionando o el origen de datos o el servicio no está disponible.|Para un servicio web o el servicio de OData, puede probar la dirección URL en Internet Explorer para comprobar si la dirección URL es correcta y que el servicio está disponible. Para una cadena de conexión de base de datos, puede usar las herramientas de conexión de datos de **Explorador de servidores** para comprobar si la cadena de conexión es válida y la base de datos está disponible. Después de restaurar la conexión, debe limpiar o volver a generar el proyecto para que el proveedor de tipos se volverá a conectar a la red.|
|**Credenciales no válidas**. Debe tener permisos válidos para el servicio web o de origen de datos.|Para una conexión de SQL, el nombre de usuario y la contraseña que se especifican en el archivo de configuración o de cadena de conexión deben ser válidos para la base de datos. Si usa la autenticación de Windows, debe tener acceso a la base de datos. El Administrador de base de datos puede identificar qué permisos para que necesita el acceso a cada base de datos y cada elemento dentro de una base de datos.<br /><br />Para un servicio web o un servicio de datos, debe tener las credenciales adecuadas. La mayoría de los proveedores de tipo proporcionan un objeto DataContext, que contiene una propiedad de las credenciales que se puede establecer con el nombre de usuario correcto y la clave de acceso.|
|**Ruta de acceso no válida**. Una ruta de acceso a un archivo no era válido.|Compruebe que la ruta de acceso es correcta y que el archivo existe. Además, debe entrecomillar correctamente cualquier backlashes en la ruta de acceso o usar una cadena de comillas triples o literales de cadenas.|

## <a name="see-also"></a>Vea también
[Proveedores de tipos](index.md)
