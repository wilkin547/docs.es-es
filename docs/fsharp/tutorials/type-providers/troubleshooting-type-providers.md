---
title: Solución de problemas en proveedores de tipos
description: 'Detectar posibles soluciones para los problemas que es más probable que encuentre al usar los proveedores de tipos en F #.'
ms.date: 05/16/2016
ms.openlocfilehash: f3b8ffdaf615563305b7b84b45a9ed1e066d0dcc
ms.sourcegitcommit: db8b83057d052c1f9f249d128b08d4423af0f7c2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/02/2018
ms.locfileid: "48873221"
---
# <a name="troubleshooting-type-providers"></a>Solución de problemas en proveedores de tipos

En este tema se describe y proporciona posibles soluciones para los problemas que es más probable que encuentre al usar los proveedores de tipos.

## <a name="possible-problems-with-type-providers"></a>Posibles problemas con los proveedores de tipos

Si se produce un problema cuando se trabaja con proveedores de tipos, puede revisar la siguiente tabla para las soluciones más comunes.

|Problema|Acciones sugeridas|
|-------|-----------------|
|**Los cambios de esquema**. Escribir proveedores funcionan mejor cuando el esquema de origen de datos es estable. Si agrega una tabla de datos o una columna o realizar otro cambio en ese esquema, el proveedor de tipos no reconoce automáticamente estos cambios.|Limpiar o recompilar el proyecto. Para limpiar el proyecto, elija **compilar**, **Clean** *ProjectName* en la barra de menús. Para volver a generar el proyecto, elija **compilar**, **recompilar** *ProjectName* en la barra de menús. Estas acciones restablecer todos los Estados del proveedor de tipo y forzar el proveedor para volver a conectarse al origen de datos y obtener información de esquema actualizado.|
|**Error de conexión**. La cadena de conexión o la dirección URL es correcta, la red está inactiva o el origen de datos o el servicio no está disponible.|Para un servicio web o servicio de OData, puede probar la dirección URL en Internet Explorer para comprobar si la dirección URL es correcta y el servicio está disponible. Una cadena de conexión de base de datos, puede usar las herramientas de conexión de datos de **Explorador de servidores** para comprobar si la cadena de conexión es válida y está disponible la base de datos. Después de restaurar la conexión, debe limpiar o recompilar el proyecto para que el proveedor de tipos se volverá a conectar a la red.|
|**Credenciales no válidas**. Debe tener permisos válidos para el servicio web o el origen de datos.|Para una conexión de SQL, el nombre de usuario y la contraseña que se especifican en el archivo de configuración o la cadena de conexión deben ser válidos para la base de datos. Si usas la autenticación de Windows, debe tener acceso a la base de datos. El Administrador de base de datos puede identificar qué permisos que necesita para tener acceso a cada base de datos y cada elemento dentro de una base de datos.<br /><br />Para un servicio web o un servicio de datos, debe tener las credenciales adecuadas. La mayoría de los proveedores de tipos proporcionan un objeto DataContext, que contiene una propiedad de las credenciales que se puede establecer con el nombre de usuario correcto y la clave de acceso.|
|**Ruta de acceso no válida**. Una ruta de acceso a un archivo no era válido.|Compruebe si la ruta de acceso es correcta y el archivo existe. Además, debe entrecomillar adecuadamente cualquier backlashes en la ruta de acceso o utilizar una cadena textual o cadenas delimitadas por comillas triples.|

## <a name="see-also"></a>Vea también

- [Proveedores de tipos](index.md)
