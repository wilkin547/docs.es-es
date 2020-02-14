---
title: Proteger acceso a métodos
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- code security, method access
- secure coding, method access
- security [.NET Framework], method access
- method access security
ms.assetid: f7c2d6ec-3b18-4e0e-9991-acd97189d818
ms.openlocfilehash: 5d083af6abc91121ebbc9554d03c635cabe2bbd9
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2020
ms.locfileid: "77217125"
---
# <a name="securing-method-access"></a>Proteger acceso a métodos
[!INCLUDE[net_security_note](../../../includes/net-security-note-md.md)]  
  
 Algunos métodos podrían no ser adecuados para llamadas desde código no seguro arbitrario. Estos métodos plantean varios riesgos: el método podría proporcionar información restringida; podría creerse cualquier información que se le pasa; podría no realizar las comprobaciones de errores en los parámetros; o bien, con los parámetros incorrectos, podría funcionar mal o hacer algo perjudicial. Debe tener en cuenta estos casos y tomar medidas para ayudar a proteger el método.  
  
 En algunos casos, deberá restringir los métodos que no están pensados para uso público pero, aún así, deben ser públicos. Por ejemplo, podría tener una interfaz a la que debe llamarse entre sus propios archivos DLL y, por tanto, debe ser pública, pero no desea exponerla públicamente para evitar que los clientes la usen o para evitar que código malintencionado use el punto de entrada del componente. Otro motivo habitual para restringir un método no pensado para uso público (pero que debe ser público) es evitar tener que documentar y dar soporte a lo que podría ser una interfaz muy interna.  
  
 El código administrado ofrece varias maneras de restringir el acceso a un método:  
  
- Limitar el ámbito de accesibilidad a la clase, el ensamblado o las clases derivadas, si son de confianza. Esta es la manera más sencilla de limitar el acceso a un método. Tenga en cuenta que, por lo general, las clases derivadas pueden ser de menos confianza que la clase de la que derivan, aunque en algunos casos compartan la identidad de la clase primaria. En concreto, no infiere la confianza de la palabra clave **Protected**, que no se utiliza necesariamente en el contexto de seguridad.  
  
- Limite el acceso al método a los llamadores de una identidad especificada; en esencia, cualquier [evidencia](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/7y5x1hcd%28v=vs.100%29) determinada (nombre seguro, publicador, zona, etc.) que elija.  
  
- Limite el acceso a un método a los llamadores que tengan los permisos que seleccione.  
  
 De forma similar, la seguridad declarativa permite controlar la herencia de clases. Puede usar **InheritanceDemand** para hacer lo siguiente:  
  
- Requerir que las clases derivadas tengan una identidad o un permiso específicos.  
  
- Requerir que las clases derivadas que invalidan métodos específicos tengan una identidad o un permiso específicos.  
  
 En el ejemplo siguiente se muestra cómo requerir que los llamadores estén firmados con un nombre seguro específico para ayudar a proteger una clase pública limitando el acceso a ella. En este ejemplo se usa el <xref:System.Security.Permissions.StrongNameIdentityPermissionAttribute> con una **petición** para el nombre seguro. Para obtener información basada en tareas sobre cómo firmar un ensamblado con un nombre seguro, vea [crear y utilizar ensamblados con nombre seguro](../../standard/assembly/create-use-strong-named.md).  
  
```vb  
<StrongNameIdentityPermissionAttribute(SecurityAction.Demand, PublicKey := "…hex…", Name := "App1", Version := "0.0.0.0")>  _  
Public Class Class1  
End Class  
```  
  
```csharp  
[StrongNameIdentityPermissionAttribute(SecurityAction.Demand, PublicKey="…hex…", Name="App1", Version="0.0.0.0")]  
public class Class1  
{  
  
}   
```  
  
## <a name="excluding-classes-and-members-from-use-by-untrusted-code"></a>Excluir clases y miembros del uso por parte de código que no sea de confianza  
 Use las declaraciones que se muestran en esta sección para evitar que código de confianza parcial use clases y métodos específicos, así como propiedades y eventos. Al aplicar estas declaraciones a una clase, se aplica la protección a todos sus métodos, propiedades y eventos; sin embargo, tenga en cuenta que la seguridad declarativa no afecta al acceso a los campos. Tenga en cuenta también que las peticiones de vínculo protegen solo frente a los llamadores inmediatos y que aún podrían sufrir ataques por señuelo.  
  
> [!NOTE]
> Se ha introducido un nuevo modelo de transparencia en el .NET Framework 4. El modelo de [código transparente en seguridad, nivel 2](security-transparent-code-level-2.md) identifica el código seguro con el atributo <xref:System.Security.SecurityCriticalAttribute>. El código crítico para la seguridad requiere que los llamadores y los herederos sean de plena confianza. Los ensamblados que se ejecutan bajo las reglas de seguridad de acceso del código desde versiones anteriores de .NET Framework pueden llamar a los ensamblados de nivel 2. En este caso, los atributos críticos para la seguridad se tratarán como peticiones de vínculo de plena confianza.  
  
 En los ensamblados con nombre seguro, se aplica una [LinkDemand](link-demands.md) a todos los métodos, propiedades y eventos accesibles públicamente para restringir su uso a los llamadores de plena confianza. Para deshabilitar esta característica, debe aplicar el atributo <xref:System.Security.AllowPartiallyTrustedCallersAttribute>. Por lo tanto, solo es necesario marcar explícitamente las clases para excluir los llamadores que no son de confianza en ensamblados no firmados o en ensamblados con este atributo; puede usar estas declaraciones para marcar en ellos un subconjunto de tipos que no están diseñados para llamadores que no son de confianza.  
  
 Los ejemplos siguientes muestran cómo impedir que código que no es de confianza use las clases y los miembros.  
  
 Para clases públicas no selladas:  
  
```vb  
<System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.InheritanceDemand, Name := "FullTrust"), _   
System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.LinkDemand, Name := "FullTrust")>  _  
Public Class CanDeriveFromMe  
End Class  
```  
  
```csharp  
[System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.InheritanceDemand, Name="FullTrust")]  
[System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.LinkDemand, Name="FullTrust")]  
public class CanDeriveFromMe  
{  
}  
```  
  
 Para clases públicas selladas:  
  
```vb  
<System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.LinkDemand, Name := "FullTrust")>  _  
NotInheritable Public Class CannotDeriveFromMe  
End Class  
```  
  
```csharp  
[System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.LinkDemand, Name="FullTrust")]  
public sealed class CannotDeriveFromMe  
{  
}  
```  
  
 Para clases públicas abstractas:  
  
```vb  
<System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.InheritanceDemand, Name := "FullTrust"), _  
System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.LinkDemand, Name := "FullTrust")>  _  
MustInherit Public Class CannotCreateInstanceOfMe_CanCastToMe  
End Class  
```  
  
```csharp  
[System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.InheritanceDemand, Name="FullTrust")]  
[System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.LinkDemand, Name="FullTrust")]  
public abstract class CannotCreateInstanceOfMe_CanCastToMe {}  
```  
  
 Para funciones públicas virtuales:  
  
```vb  
Class Base1   
<System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.InheritanceDemand, Name:="FullTrust"), System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.LinkDemand, Name:="FullTrust")> _  
    Public Overridable Sub CanOverrideOrCallMe()  
    End Sub 'CanOverrideOrCallMe  
End Class 'Base1  
```  
  
```csharp  
class Base1   
{  
[System.Security.Permissions.PermissionSetAttribute(  
System.Security.Permissions.SecurityAction.InheritanceDemand, Name="FullTrust")]  
[System.Security.Permissions.PermissionSetAttribute(  
System.Security.Permissions.SecurityAction.LinkDemand, Name="FullTrust")]  
    public virtual void CanOverrideOrCallMe() {}  
}  
```  
  
 Para funciones públicas abstractas:  
  
```vb  
MustInherit Class Base2  
    <System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.InheritanceDemand, Name:="FullTrust"), System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.LinkDemand, Name:="FullTrust")> _  
    Public Sub MustOverrideMe()  
    End Sub  
End Class 'Base2  
```  
  
```csharp  
abstract class Base2 {  
[System.Security.Permissions.PermissionSetAttribute(  
System.Security.Permissions.SecurityAction.InheritanceDemand, Name = "FullTrust")]  
[System.Security.Permissions.PermissionSetAttribute(  
System.Security.Permissions.SecurityAction.LinkDemand, Name = "FullTrust")]  
public abstract void MustOverrideMe();  
}  
```  
  
 Para funciones de invalidación públicas en las que la clase base no solicita plena confianza:  
  
```vb  
Class Derived  
    Inherits Base1  
<System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.Demand, Name:="FullTrust")> _  
    Public Overrides Sub CanOverrideOrCallMe()  
        MyBase.CanOverrideOrCallMe()  
    End Sub 'CanOverrideOrCallMe  
End Class 'Derived  
```  
  
```csharp  
class Derived : Base1  
{     
[System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.Demand, Name="FullTrust")]      
    public override void CanOverrideOrCallMe()   
    {  
        base.CanOverrideOrCallMe();  
    }  
}  
```  
  
 Para funciones de invalidación públicas en las que la clase base solicita plena confianza:  
  
```vb  
Class Derived  
    Inherits Base1  
<System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.LinkDemand, Name:="FullTrust")> _  
    Public Overrides Sub CanOverrideOrCallMe()  
        MyBase.CanOverrideOrCallMe()  
    End Sub 'CanOverrideOrCallMe   
End Class 'Derived  
```  
  
```csharp  
class Derived : Base1  
{     
[System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.LinkDemand, Name="FullTrust")]      
    public override void CanOverrideOrCallMe()   
    {  
        base.CanOverrideOrCallMe();  
    }  
}  
```  
  
 Para interfaces públicas:  
  
```vb  
Public Interface ICanCastToMe  
    <System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.LinkDemand, Name:="FullTrust"), System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.InheritanceDemand, Name:="FullTrust")> _  
    Sub CanImplementMe()  
End Interface 'ICanCastToMe  
<System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.LinkDemand, Name:="FullTrust"), System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.InheritanceDemand, Name:="FullTrust")> _  
Class Implemented  
    Implements ICanCastToMe  
    Public Sub CanImplementMe()  
    End Sub 'CanImplementMe  
```  
  
```csharp  
public interface ICanCastToMe   
{  
[System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.LinkDemand, Name = "FullTrust")]  
[System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.InheritanceDemand, Name = "FullTrust")]  
void CanImplementMe();  
}  
[System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.LinkDemand, Name = "FullTrust")]  
[System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.InheritanceDemand, Name = "FullTrust")]  
class Implemented : ICanCastToMe  
{  
    public void CanImplementMe()  
    {  
    }  
}  
```  
  
## <a name="virtual-internal-overrides-or-overloads-overridable-friend"></a>Reemplazos internos virtuales o amigo reemplazable de sobrecargas  
  
> [!NOTE]
> En esta sección se advierte sobre un problema de seguridad cuando se declara un método como `virtual` y `internal` (`Overloads` `Overridable` `Friend` en Visual Basic). Esta advertencia solo se aplica a las versiones 1,0 y 1,1 de .NET Framework, no se aplica a las versiones posteriores.  
  
 En las versiones 1,0 y 1,1 de .NET Framework, debe tener en cuenta un Matic de la accesibilidad del sistema de tipos al confirmar que el código no está disponible para otros ensamblados. Un método que se declara **virtual** e **Internal** (**overloads Overridable Friend** en Visual Basic) puede invalidar la entrada vtable de la clase primaria y solo se puede usar dentro del mismo ensamblado porque es interno. Sin embargo, la accesibilidad para el reemplazo viene determinada por la palabra clave **virtual** , y se puede invalidar desde otro ensamblado siempre y cuando ese código tenga acceso a la propia clase. Si la posibilidad de una invalidación supone un problema, use la seguridad declarativa para corregirlo o quite la palabra clave **virtual** si no es estrictamente necesaria.  
  
 Tenga en cuenta que aunque un compilador de lenguaje impida estas invalidaciones con un error de compilación, el código escrito con otros compiladores podría realizar la invalidación.  
  
## <a name="see-also"></a>Consulte también

- [Instrucciones de codificación segura](../../standard/security/secure-coding-guidelines.md)
