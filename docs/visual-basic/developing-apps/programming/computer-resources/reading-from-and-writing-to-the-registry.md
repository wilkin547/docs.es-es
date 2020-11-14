---
title: Leer y escribir en el Registro
ms.date: 07/20/2015
helpviewer_keywords:
- My.Computer.Registry object, tasks
- registry [Visual Basic], writing to
- registry [Visual Basic], reading
ms.assetid: a13da106-185b-41d7-b23c-416da65e21e4
ms.openlocfilehash: fe0714f25cd41ca9ce4eabf135c82d1dbb1fe524
ms.sourcegitcommit: 74d05613d6c57106f83f82ce8ee71176874ea3f0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2020
ms.locfileid: "93282221"
---
# <a name="reading-from-and-writing-to-the-registry-visual-basic"></a>Leer y escribir en el Registro (Visual Basic)

En este tema se describen las tareas y los temas conceptuales asociados al Registro.  
  
 Al programar en Visual Basic, puede optar por acceder al registro mediante las funciones proporcionadas por Visual Basic o mediante las clases del registro de .NET. El Registro hospeda información del sistema operativo, así como de las aplicaciones hospedadas en el equipo. Si trabaja con el Registro, puede poner en peligro la seguridad al permitir accesos inadecuados a recursos del sistema o a información protegida.  
  
## <a name="in-this-section"></a>En esta sección  

 [Crear una clave del Registro y establecer su valor](how-to-create-a-registry-key-and-set-its-value.md)  
 Describe cómo usar los métodos `CreateSubKey` y `SetValue` del objeto `My.Computer.Registry` para crear una clave del Registro y establecer su valor.  
  
 [Leer un valor a partir de una clave del Registro](how-to-read-a-value-from-a-registry-key.md)  
 Describe cómo usar el método `GetValue` del objeto `My.Computer.Registry` para leer un valor de una clave del Registro.  
  
 [Eliminar una clave del Registro](how-to-delete-a-registry-key.md)  
 Describe cómo usar el método `DeleteSubKey` de la propiedad `My.Computer.Registry.CurrentUser` para eliminar una clave del Registro.  
  
 [Leer y escribir en el Registro mediante Microsoft.Win32 Namespace](reading-from-and-writing-to-the-registry-using-the-microsoft-win32-namespace.md)  
 Describe cómo usar las clases `Registry` y `RegistryKey` de .NET para acceder al registro.  
  
 [Seguridad y Registro](security-and-the-registry.md)  
 Describe problemas de seguridad que afectan al Registro.  
  
## <a name="related-sections"></a>Secciones relacionadas  

 <xref:Microsoft.VisualBasic.MyServices.RegistryProxy>  
 Enumera y explica los miembros del objeto `My.Computer.Registry`.  
  
 <xref:Microsoft.Win32.Registry>  
 Ofrece información general sobre la clase `Registry`, junto con vínculos a claves y miembros individuales.
