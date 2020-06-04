---
title: Mgmtclassgen.exe (Generador de clases fuertemente tipadas para administración)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- CIM types
- Management Strongly Typed Class Generator
- WMI class
- Mgmtclassgen.exe
- early-bound managed classes
ms.assetid: 02ce6699-49b5-4a0b-b0d5-1003c491232e
ms.openlocfilehash: d6de28694a1fdcd22cc2baa8cff66387c601414c
ms.sourcegitcommit: 71b8f5a2108a0f1a4ef1d8d75c5b3e129ec5ca1e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/29/2020
ms.locfileid: "84201861"
---
# <a name="mgmtclassgenexe-management-strongly-typed-class-generator"></a>Mgmtclassgen.exe (Generador de clases fuertemente tipadas para administración)
La herramienta Generador de clases fuertemente tipadas para administración permite generar con rapidez una clase administrada en tiempo de compilación para una clase especificada de Instrumental de administración de Windows (WMI). La clase generada simplifica el código que se debe escribir para tener acceso a una instancia de la clase de WMI.  
  
## <a name="syntax"></a>Sintaxis  
  
```console  
mgmtclassgen
WMIClass [options]
```  
  
|Argumento|Descripción|  
|--------------|-----------------|  
|*WMIClass*|Clase de Instrumental de administración de Windows para la que se genera una clase administrada en tiempo de compilación.|  
  
|Opción|Descripción|  
|------------|-----------------|  
|**/l**  *language*|Especifica el lenguaje en el que se genera la clase administrada en tiempo de compilación. Puede especificar **CS** (C#, predeterminado), **VB** (Visual Basic), **MC** (C++) o **JS** (JScript) como argumento del lenguaje.|  
|**/m**  *machine*|Especifica el equipo con el que se va a conectar y en el que reside la clase de WMI. La opción predeterminada es el equipo local.|  
|**/n**  *path*|Especifica la ruta de acceso al espacio de nombres de WMI que contiene la clase de WMI. Si no se especifica esta opción, la herramienta genera código para *WMIClass* en el espacio de nombres **Root\cimv2** predeterminado.|  
|**/o**  *classnamespace*|Especifica el espacio de nombres de .NET en el que se genera la clase de código administrado. Si no se especifica esta opción, la herramienta genera el espacio de nombres utilizando el espacio de nombres de WMI y el prefijo de esquema. El prefijo de esquema es la parte del nombre de clase que figura delante del carácter de subrayado. Por ejemplo, para la clase **Win32_OperatingSystem** del espacio de nombres **Root\cimv2**, la herramienta generaría la clase en **ROOT.CIMV2.Win32**.|  
|**/p**  *filepath*|Especifica la ruta de acceso al archivo donde se guarda el código generado. Si no se especifica esta opción, la herramienta crea el archivo en el directorio actual. Asigna un nombre a la clase y al archivo donde se genera la clase mediante el argumento *WMIClass*. El nombre de la clase y el nombre del archivo coinciden con el nombre de *WMIClass*. Si *WMIClass* contiene un carácter de subrayado, la herramienta usa la parte del nombre de clase que figura detrás del carácter de subrayado. Por ejemplo, si el nombre de *WMIClass* tiene el formato **Win32_LogicalDisk**, el nombre de la clase generada y del archivo es "logicaldisk". Si ya existe un archivo, la herramienta sobrescribe el archivo existente.|  
|**/pw**  *password*|Especifica la contraseña que se usa al iniciar sesión en el equipo especificado con la opción **/m**.|  
|**/u**  *user name*|Especifica el nombre de usuario que se usa al iniciar sesión en el equipo especificado con la opción **/m**.|  
|**/?**|Muestra las opciones y la sintaxis de los comandos para la herramienta.|  
  
## <a name="remarks"></a>Comentarios  
 Mgmtclassgen.exe usa el método <xref:System.Management.ManagementClass.GetStronglyTypedClassCode%2A?displayProperty=nameWithType>. Por tanto, se puede utilizar cualquier proveedor de código personalizado para generar código en lenguajes administrados distintos de C#, Visual Basic y JScript.  
  
 Tenga en cuenta que las clases generadas se enlazan al esquema para el que se generan. Si el esquema subyacente cambia, se debe volver a generar la clase para que los cambios se reflejen en el esquema.  
  
 La tabla siguiente muestra cómo se asignan los tipos del Modelo de información común (CIM) de WMI a los tipos de datos en una clase generada:  
  
|Tipo de CIM|Tipo de datos en la clase generada|  
|--------------|--------------------------------------|  
|CIM_SINT8|**SByte**|  
|CIM_UINT8|**Byte**|  
|CIM_SINT16|**Int16**|  
|CIM_UINT16|**UInt16**|  
|CIM_SINT32|**Int32**|  
|SIM_UINT32|**UInt32**|  
|CIM_SINT64|**Int64**|  
|CIM_UINT64|**UInt64**|  
|CIM_REAL32|**Single**|  
|CIM_REAL64|**Double**|  
|CIM_BOOLEAN|**Boolean**|  
|CIM_String|**String**|  
|CIM_DATETIME|**DateTime** o **TimeSpan**|  
|CIM_REFERENCE|**ManagementPath**|  
|CIM_CHAR16|**Char**|  
|CIM_OBJECT|**ManagementBaseObject**|  
|CIM_IUNKNOWN|**Objeto**|  
|CIM_ARRAY|Matriz de los objetos mencionados anteriormente|  
  
 Tenga en cuenta los comportamientos siguientes cuando se genera una clase WMI:  
  
- Es posible que un método o una propiedad públicos estándar tengan el mismo nombre que un método o una propiedad existentes. Si esto sucede, la herramienta cambia el nombre del método o de la propiedad en la clase generada para evitar conflictos de nombres.  
  
- Es posible que el nombre de un método o de una propiedad en una clase generada sea una palabra clave en el lenguaje de programación de destino. Si esto sucede, la herramienta cambia el nombre del método o de la propiedad en la clase generada para evitar conflictos de nombres.  
  
- En WMI, los calificadores son modificadores que contienen información para describir una clase, una instancia, una propiedad o un método. WMI usa calificadores estándar como **Read**, **Write** y **Key** para describir una propiedad en una clase generada. Por ejemplo, una propiedad que se modifica con un calificador **Read** se define únicamente con un descriptor de acceso **get** de propiedad en la clase generada. Como las propiedades marcadas con el calificador **Read** están diseñadas para ser de solo lectura, no se define ningún descriptor de acceso **set**.  
  
- Una propiedad numérica se puede modificar mediante los calificadores **Values** y **ValueMaps** para indicar que la propiedad solo se puede establecer en valores permisibles especificados. Con estos calificadores **Values** y **ValueMaps** se genera una enumeración y se asigna la propiedad a la enumeración.  
  
- WMI utiliza el término singleton para describir una clase que solo puede tener una instancia. Por tanto, el constructor sin parámetros para una clase singleton inicializará la clase en la única instancia de la misma.  
  
- Una clase WMI puede tener propiedades que sean objetos. Cuando se genera una clase fuertemente tipada para este tipo de clase WMI, se debe considerar la posibilidad de generar clases fuertemente tipadas para los tipos de las propiedades de objetos insertados. Esto permitirá acceder a los objetos insertados de un modo fuertemente tipado. Tenga en cuenta que existe la posibilidad de que el código generado no pueda detectar el tipo del objeto incrustado. En este caso, se creará un comentario en el código generado para informar al usuario de este punto. A continuación, se puede modificar el código generado para que el tipo de la propiedad corresponda a la otra clase generada.  
  
- En WMI, el valor de los datos del tipo de datos CIM_DATETIME puede representar una fecha y hora específicas o un intervalo de tiempo. Si el valor de los datos representa una fecha y hora, el tipo de datos de la clase generada es **DateTime**. Si el valor de los datos representa un intervalo de tiempo, el tipo de datos de la clase generada es **TimeSpan**.  
  
 Otra posibilidad consiste en generar una clase fuertemente tipada mediante la extensión de administración del explorador de servidores en Visual Studio .NET.  
  
 Para obtener más información sobre WMI, vea el tema sobre **Instrumental de administración de Windows** en la documentación de Platform SDK.  
  
## <a name="examples"></a>Ejemplos  
 El siguiente comando genera una clase administrada en código de C# para la clase WMI **Win32_LogicalDisk** en el espacio de nombres **Root\cimv2**. La herramienta escribe la clase administrada en el archivo de código fuente en c:\disk.cs en el espacio de nombres **ROOT.CIMV2.Win32**.  
  
```console  
mgmtclassgen Win32_LogicalDisk /n root\cimv2 /l CS /p c:\disk.cs  
```  
  
 En el ejemplo de código siguiente se muestra la forma de utilizar mediante programación una clase generada. En primer lugar, se enumera una instancia de la clase y se imprime la ruta de acceso. A continuación, se crea una instancia de la clase generada que se va a inicializar con una instancia de WMI. `Process` es la clase generada para **Win32_Process** y `LogicalDisk` es la clase generada para **Win32_LogicalDisk** en el espacio de nombres **Root\cimv2**.  
  
```vb  
Imports System  
Imports System.Management  
Imports ROOT.CIMV2.Win32  
  
Public Class App
   Public Shared Sub Main()
      ' Enumerate instances of the Win32_process.  
      ' Print the Name property of the instance.  
      Dim ps As Process
      For Each ps In  Process.GetInstances()  
         Console.WriteLine(ps.Name)  
      Next ps  
  
      ' Initialize the instance of LogicalDisk with  
      ' the WMI instance pointing to logical drive d:.  
      Dim dskD As New LogicalDisk(New _  
         ManagementPath("win32_LogicalDisk.DeviceId=""d:"""))  
      Console.WriteLine(dskD.Caption)  
   End Sub  
End Class  
```  
  
```csharp  
using System;  
using System.Management;  
using ROOT.CIMV2.Win32;  
  
public class App  
{  
   public static void Main()  
   {  
      // Enumerate instances of the Win32_process.  
      // Print the Name property of the instance.  
      foreach(Process ps in Process.GetInstances())  
      {  
         Console.WriteLine(ps.Name);  
      }  
  
      // Initialize the instance of LogicalDisk with  
      // the WMI instance pointing to logical drive d:.  
      LogicalDisk dskD = new LogicalDisk(new ManagementPath(  
        "win32_LogicalDisk.DeviceId=\"d:\""));  
      Console.WriteLine(dskD.Caption);  
   }  
}  
```  
  
## <a name="see-also"></a>Vea también

- <xref:System.Management>
- <xref:System.Management.ManagementClass.GetStronglyTypedClassCode%2A?displayProperty=nameWithType>
- <xref:System.CodeDom.Compiler.CodeDomProvider?displayProperty=nameWithType>
- [Herramientas](index.md)
- [Símbolos del sistema](developer-command-prompt-for-vs.md)
