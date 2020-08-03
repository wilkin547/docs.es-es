---
title: Clrver.exe (herramienta de versión de CLR)
description: Revise Clrver.exe, la herramienta de versión de CLR. Esta herramienta notifica todas las versiones instaladas de Common Language Runtime (CLR) en el equipo.
ms.date: 03/30/2017
helpviewer_keywords:
- Clrver.exe
- CLR Version tool
ms.assetid: cbc2ee86-bdc8-4a65-a8f1-ba23bce3a699
ms.openlocfilehash: e914034819418df00438c454e209e6c86779ba3c
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2020
ms.locfileid: "87167274"
---
# <a name="clrverexe-clr-version-tool"></a>Clrver.exe (herramienta de versión de CLR)
La herramienta de versión de CLR (Clrver.exe) notifica todas las versiones instaladas de Common Language Runtime (CLR) en el equipo.  
  
 Esta herramienta se instala automáticamente con Visual Studio. Para ejecutar la herramienta, use Símbolo del sistema para desarrolladores de Visual Studio (o Símbolo del sistema de Visual Studio en Windows 7). Para más información, consulte [Símbolos del sistema](developer-command-prompt-for-vs.md).  
  
 En el símbolo del sistema, escriba lo siguiente:  
  
## <a name="syntax"></a>Sintaxis  
  
```console  
clrver [option]  
```  
  
## <a name="options"></a>Opciones  
  
|Opción|Descripción|  
|------------|-----------------|  
|`-all`|Muestra todos los procesos del equipo que usan CLR.|  
|*pid*|Muestra las versiones de CLR que utiliza el proceso con el identificador de proceso especificado (PID).|  
|`-?`|Muestra las opciones y la sintaxis de los comandos para la herramienta.|  
  
## <a name="remarks"></a>Comentarios  
 Si llama a Clrver.exe sin opciones, este muestra todas las versiones instaladas de CLR. Si se especifica un PID para otro usuario, debe tener permisos administrativos para obtener la información de versión.  
  
> [!NOTE]
> En Windows Vista y versiones posteriores, el Control de cuentas de usuario (UAC) determina los privilegios de un usuario. Si es miembro del grupo Administradores integrados, se le asignarán dos símbolos (tokens) de acceso en tiempo de ejecución: un símbolo (token) de acceso de usuario estándar y un símbolo (token) de acceso de administrador. De forma predeterminada, se le asignará el rol de usuario estándar. Para ejecutar código que requiere permisos administrativos, primero debe elevar el nivel de sus privilegios de usuario estándar a administrador. Para ello, inicie el símbolo del sistema haciendo clic con el botón secundario en el icono de dicho símbolo e indicando que desea ejecutarlo como administrador.  
  
 Al intentar determinar la versión de CLR para los procesos SYSTEM, LOCAL SERVICE y NETWORK SERVICE aparece un mensaje que indica que el PID no existe.  
  
## <a name="examples"></a>Ejemplos  
 El comando siguiente muestra todas las versiones de CLR instaladas en el equipo.  
  
 `clrver`  
  
 El comando siguiente muestra la versión de CLR que usa el proceso 128.  
  
 `clrver 128`  
  
 El comando siguiente muestra todos los procesos administrados y la versión de CLR que usan.  
  
 `Clrver -all`  
  
## <a name="see-also"></a>Vea también

- [Herramientas](index.md)
- [Símbolos del sistema](developer-command-prompt-for-vs.md)
