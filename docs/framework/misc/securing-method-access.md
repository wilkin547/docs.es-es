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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b0d9ddbd6c7b027a7c342f4c14192a7571beb592
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33397889"
---
# <a name="securing-method-access"></a><span data-ttu-id="aecf2-102">Proteger acceso a métodos</span><span class="sxs-lookup"><span data-stu-id="aecf2-102">Securing Method Access</span></span>
[!INCLUDE[net_security_note](../../../includes/net-security-note-md.md)]  
  
 <span data-ttu-id="aecf2-103">Algunos métodos podrían no ser adecuados para llamadas desde código no seguro arbitrario.</span><span class="sxs-lookup"><span data-stu-id="aecf2-103">Some methods might not be suitable to allow arbitrary untrusted code to call.</span></span> <span data-ttu-id="aecf2-104">Estos métodos plantean varios riesgos: el método podría proporcionar información restringida; podría creerse cualquier información que se le pasa; podría no realizar las comprobaciones de errores en los parámetros; o bien, con los parámetros incorrectos, podría funcionar mal o hacer algo perjudicial.</span><span class="sxs-lookup"><span data-stu-id="aecf2-104">Such methods pose several risks: The method might provide some restricted information; it might believe any information passed to it; it might not do error checking on the parameters; or with the wrong parameters, it might malfunction or do something harmful.</span></span> <span data-ttu-id="aecf2-105">Debe tener en cuenta estos casos y tomar medidas para ayudar a proteger el método.</span><span class="sxs-lookup"><span data-stu-id="aecf2-105">You should be aware of these cases and take action to help protect the method.</span></span>  
  
 <span data-ttu-id="aecf2-106">En algunos casos, deberá restringir los métodos que no están pensados para uso público pero, aún así, deben ser públicos.</span><span class="sxs-lookup"><span data-stu-id="aecf2-106">In some cases, you might need to restrict methods that are not intended for public use but still must be public.</span></span> <span data-ttu-id="aecf2-107">Por ejemplo, podría tener una interfaz a la que debe llamarse entre sus propios archivos DLL y, por tanto, debe ser pública, pero no desea exponerla públicamente para evitar que los clientes la usen o para evitar que código malintencionado use el punto de entrada del componente.</span><span class="sxs-lookup"><span data-stu-id="aecf2-107">For example, you might have an interface that needs to be called across your own DLLs and hence must be public, but you do not want to expose it publicly to prevent customers from using it or to prevent malicious code from exploiting the entry point into your component.</span></span> <span data-ttu-id="aecf2-108">Otro motivo habitual para restringir un método no pensado para uso público (pero que debe ser público) es evitar tener que documentar y dar soporte a lo que podría ser una interfaz muy interna.</span><span class="sxs-lookup"><span data-stu-id="aecf2-108">Another common reason to restrict a method not intended for public use (but that must be public) is to avoid having to document and support what might be a very internal interface.</span></span>  
  
 <span data-ttu-id="aecf2-109">El código administrado ofrece varias maneras de restringir el acceso a un método:</span><span class="sxs-lookup"><span data-stu-id="aecf2-109">Managed code offers several ways to restrict method access:</span></span>  
  
-   <span data-ttu-id="aecf2-110">Limitar el ámbito de accesibilidad a la clase, el ensamblado o las clases derivadas, si son de confianza.</span><span class="sxs-lookup"><span data-stu-id="aecf2-110">Limit the scope of accessibility to the class, assembly, or derived classes, if they can be trusted.</span></span> <span data-ttu-id="aecf2-111">Esta es la manera más sencilla de limitar el acceso a un método.</span><span class="sxs-lookup"><span data-stu-id="aecf2-111">This is the simplest way to limit method access.</span></span> <span data-ttu-id="aecf2-112">Tenga en cuenta que, por lo general, las clases derivadas pueden ser de menos confianza que la clase de la que derivan, aunque en algunos casos compartan la identidad de la clase primaria.</span><span class="sxs-lookup"><span data-stu-id="aecf2-112">Note that, in general, derived classes can be less trustworthy than the class they derive from, though in some cases they share the parent class's identity.</span></span> <span data-ttu-id="aecf2-113">En concreto, no deduzca confianza de la palabra clave **protegido**, que no se usa necesariamente en el contexto de seguridad.</span><span class="sxs-lookup"><span data-stu-id="aecf2-113">In particular, do not infer trust from the keyword **protected**, which is not necessarily used in the security context.</span></span>  
  
-   <span data-ttu-id="aecf2-114">Limitar el acceso a un método a llamadores de una identidad específica; básicamente, cualquier determinado [evidencia](http://msdn.microsoft.com/library/64ceb7c8-a0b4-46c4-97dc-6c22da0539da) (nombre seguro, publicador, zona etc.) elija.</span><span class="sxs-lookup"><span data-stu-id="aecf2-114">Limit the method access to callers of a specified identity--essentially, any particular [evidence](http://msdn.microsoft.com/library/64ceb7c8-a0b4-46c4-97dc-6c22da0539da) (strong name, publisher, zone, and so on) you choose.</span></span>  
  
-   <span data-ttu-id="aecf2-115">Limite el acceso a un método a los llamadores que tengan los permisos que seleccione.</span><span class="sxs-lookup"><span data-stu-id="aecf2-115">Limit the method access to callers having whatever permissions you select.</span></span>  
  
 <span data-ttu-id="aecf2-116">De forma similar, la seguridad declarativa permite controlar la herencia de clases.</span><span class="sxs-lookup"><span data-stu-id="aecf2-116">Similarly, declarative security allows you to control inheritance of classes.</span></span> <span data-ttu-id="aecf2-117">Puede usar **InheritanceDemand** para hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="aecf2-117">You can use **InheritanceDemand** to do the following:</span></span>  
  
-   <span data-ttu-id="aecf2-118">Requerir que las clases derivadas tengan una identidad o un permiso específicos.</span><span class="sxs-lookup"><span data-stu-id="aecf2-118">Require derived classes to have a specified identity or permission.</span></span>  
  
-   <span data-ttu-id="aecf2-119">Requerir que las clases derivadas que invalidan métodos específicos tengan una identidad o un permiso específicos.</span><span class="sxs-lookup"><span data-stu-id="aecf2-119">Require derived classes that override specific methods to have a specified identity or permission.</span></span>  
  
 <span data-ttu-id="aecf2-120">En el ejemplo siguiente se muestra cómo requerir que los llamadores estén firmados con un nombre seguro específico para ayudar a proteger una clase pública limitando el acceso a ella.</span><span class="sxs-lookup"><span data-stu-id="aecf2-120">The following example shows how to help protect a public class for limited access by requiring that callers be signed with a particular strong name.</span></span> <span data-ttu-id="aecf2-121">Este ejemplo se utiliza la <xref:System.Security.Permissions.StrongNameIdentityPermissionAttribute> con un **petición** para el nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="aecf2-121">This example uses the <xref:System.Security.Permissions.StrongNameIdentityPermissionAttribute> with a **Demand** for the strong name.</span></span> <span data-ttu-id="aecf2-122">Para obtener información basada en tareas acerca de cómo firmar un ensamblado con un nombre seguro, vea [crear y utilizar ensamblados](../../../docs/framework/app-domains/create-and-use-strong-named-assemblies.md).</span><span class="sxs-lookup"><span data-stu-id="aecf2-122">For task-based information on how to sign an assembly with a strong name, see [Creating and Using Strong-Named Assemblies](../../../docs/framework/app-domains/create-and-use-strong-named-assemblies.md).</span></span>  
  
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
  
## <a name="excluding-classes-and-members-from-use-by-untrusted-code"></a><span data-ttu-id="aecf2-123">Excluir clases y miembros del uso por parte de código que no sea de confianza</span><span class="sxs-lookup"><span data-stu-id="aecf2-123">Excluding Classes and Members from Use by Untrusted Code</span></span>  
 <span data-ttu-id="aecf2-124">Use las declaraciones que se muestran en esta sección para evitar que código de confianza parcial use clases y métodos específicos, así como propiedades y eventos.</span><span class="sxs-lookup"><span data-stu-id="aecf2-124">Use the declarations shown in this section to prevent specific classes and methods, as well as properties and events, from being used by partially trusted code.</span></span> <span data-ttu-id="aecf2-125">Al aplicar estas declaraciones a una clase, se aplica la protección a todos sus métodos, propiedades y eventos; sin embargo, tenga en cuenta que la seguridad declarativa no afecta al acceso a los campos.</span><span class="sxs-lookup"><span data-stu-id="aecf2-125">By applying these declarations to a class, you apply the protection to all its methods, properties, and events; however, note that field access is not affected by declarative security.</span></span> <span data-ttu-id="aecf2-126">Tenga en cuenta también que las peticiones de vínculo protegen solo frente a los llamadores inmediatos y que aún podrían sufrir ataques por señuelo.</span><span class="sxs-lookup"><span data-stu-id="aecf2-126">Note also that link demands help protect against only the immediate callers and might still be subject to luring attacks.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="aecf2-127">Se ha incorporado un nuevo modelo de transparencia en [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="aecf2-127">A new transparency model has been introduced in the [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)].</span></span> <span data-ttu-id="aecf2-128">El [código transparente en seguridad, nivel 2](../../../docs/framework/misc/security-transparent-code-level-2.md) modelo identifica el código seguro con el <xref:System.Security.SecurityCriticalAttribute> atributo.</span><span class="sxs-lookup"><span data-stu-id="aecf2-128">The [Security-Transparent Code, Level 2](../../../docs/framework/misc/security-transparent-code-level-2.md) model identifies secure code with the <xref:System.Security.SecurityCriticalAttribute> attribute.</span></span> <span data-ttu-id="aecf2-129">El código crítico para la seguridad requiere que los llamadores y los herederos sean de plena confianza.</span><span class="sxs-lookup"><span data-stu-id="aecf2-129">Security-critical code requires both callers and inheritors to be fully trusted.</span></span> <span data-ttu-id="aecf2-130">Los ensamblados que se ejecutan bajo las reglas de seguridad de acceso del código desde versiones anteriores de .NET Framework pueden llamar a los ensamblados de nivel 2.</span><span class="sxs-lookup"><span data-stu-id="aecf2-130">Assemblies that are running under the code access security rules from earlier .NET Framework versions can call level 2 assemblies.</span></span> <span data-ttu-id="aecf2-131">En este caso, los atributos críticos para la seguridad se tratarán como peticiones de vínculo de plena confianza.</span><span class="sxs-lookup"><span data-stu-id="aecf2-131">In this case, the security-critical attributes will be treated as link demands for full trust.</span></span>  
  
 <span data-ttu-id="aecf2-132">En los ensamblados con nombre seguro, una [LinkDemand](../../../docs/framework/misc/link-demands.md) se aplica a todos los métodos accesibles públicamente, propiedades y eventos en él para restringir su uso a llamadores de plena confianza.</span><span class="sxs-lookup"><span data-stu-id="aecf2-132">In strong-named assemblies, a [LinkDemand](../../../docs/framework/misc/link-demands.md) is applied to all publicly accessible methods, properties, and events therein to restrict their use to fully trusted callers.</span></span> <span data-ttu-id="aecf2-133">Para deshabilitar esta característica, debe aplicar el atributo <xref:System.Security.AllowPartiallyTrustedCallersAttribute>.</span><span class="sxs-lookup"><span data-stu-id="aecf2-133">To disable this feature, you must apply the <xref:System.Security.AllowPartiallyTrustedCallersAttribute> attribute.</span></span> <span data-ttu-id="aecf2-134">Por lo tanto, solo es necesario marcar explícitamente las clases para excluir los llamadores que no son de confianza en ensamblados no firmados o en ensamblados con este atributo; puede usar estas declaraciones para marcar en ellos un subconjunto de tipos que no están diseñados para llamadores que no son de confianza.</span><span class="sxs-lookup"><span data-stu-id="aecf2-134">Thus, explicitly marking classes to exclude untrusted callers is necessary only for unsigned assemblies or assemblies with this attribute; you can use these declarations to mark a subset of types therein that are not intended for untrusted callers.</span></span>  
  
 <span data-ttu-id="aecf2-135">Los ejemplos siguientes muestran cómo impedir que código que no es de confianza use las clases y los miembros.</span><span class="sxs-lookup"><span data-stu-id="aecf2-135">The following examples show how to prevent classes and members from being used by untrusted code.</span></span>  
  
 <span data-ttu-id="aecf2-136">Para clases públicas no selladas:</span><span class="sxs-lookup"><span data-stu-id="aecf2-136">For public nonsealed classes:</span></span>  
  
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
  
 <span data-ttu-id="aecf2-137">Para clases públicas selladas:</span><span class="sxs-lookup"><span data-stu-id="aecf2-137">For public sealed classes:</span></span>  
  
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
  
 <span data-ttu-id="aecf2-138">Para clases públicas abstractas:</span><span class="sxs-lookup"><span data-stu-id="aecf2-138">For public abstract classes:</span></span>  
  
```vb  
<System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.InheritanceDemand, Name := "FullTrust"), _  
System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.LinkDemand, Name := "FullTrust")>  _  
MustInherit Public Class CannotCreateInstanceOfMe_CanCastToMe  
End Class  
```  
  
```csharp  
[System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.InheritanceDemand, Name="FullTrust")]  
[System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.LinkDemand, Name="FullTrust")]  
public abstract class CannotCreateInstanceOfMe_CanCastToMe{}  
```  
  
 <span data-ttu-id="aecf2-139">Para funciones públicas virtuales:</span><span class="sxs-lookup"><span data-stu-id="aecf2-139">For public virtual functions:</span></span>  
  
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
  
 <span data-ttu-id="aecf2-140">Para funciones públicas abstractas:</span><span class="sxs-lookup"><span data-stu-id="aecf2-140">For public abstract functions:</span></span>  
  
```vb  
MustInherit Class Base2  
    <System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.InheritanceDemand, Name:="FullTrust"), System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.LinkDemand, Name:="FullTrust")> _  
    Public Sub MustOverrideMe()  
    End Sub  
End Class 'Base2  
```  
  
```csharp  
abstract class Base2{  
[System.Security.Permissions.PermissionSetAttribute(  
System.Security.Permissions.SecurityAction.InheritanceDemand, Name = "FullTrust")]  
[System.Security.Permissions.PermissionSetAttribute(  
System.Security.Permissions.SecurityAction.LinkDemand, Name = "FullTrust")]  
public abstract void MustOverrideMe();  
}  
```  
  
 <span data-ttu-id="aecf2-141">Para funciones de invalidación públicas en las que la clase base no solicita plena confianza:</span><span class="sxs-lookup"><span data-stu-id="aecf2-141">For public override functions where the base class does not demand full trust:</span></span>  
  
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
  
 <span data-ttu-id="aecf2-142">Para funciones de invalidación públicas en las que la clase base solicita plena confianza:</span><span class="sxs-lookup"><span data-stu-id="aecf2-142">For public override functions where the base class demands full trust:</span></span>  
  
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
  
 <span data-ttu-id="aecf2-143">Para interfaces públicas:</span><span class="sxs-lookup"><span data-stu-id="aecf2-143">For public interfaces:</span></span>  
  
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
  
## <a name="virtual-internal-overrides-or-overloads-overridable-friend"></a><span data-ttu-id="aecf2-144">Reemplazos internos virtuales o amigo reemplazable de sobrecargas</span><span class="sxs-lookup"><span data-stu-id="aecf2-144">Virtual Internal Overrides or Overloads Overridable Friend</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="aecf2-145">En esta sección se advierte sobre un problema de seguridad cuando se declara un método como `virtual` y `internal` (`Overloads``Overridable``Friend` en Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="aecf2-145">This section warns about a security issue when declaring a method as both `virtual` and `internal` (`Overloads``Overridable``Friend` in Visual Basic).</span></span> <span data-ttu-id="aecf2-146">Esta advertencia solo se aplica a las versiones 1.0 y 1.1 de .NET Framework, no se aplica a las versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="aecf2-146">This warning applies only to the .NET Framework versions 1.0 and 1.1, it does not apply to later versions.</span></span>  
  
 <span data-ttu-id="aecf2-147">En las versiones 1.0 y 1.1 de .NET Framework, debe tener en cuenta un matiz de la accesibilidad del sistema de tipos cuando se confirma que el código no está disponible para otros ensamblados.</span><span class="sxs-lookup"><span data-stu-id="aecf2-147">In the .NET Framework versions 1.0 and 1.1, you must be aware of a nuance of the type system accessibility when confirming that your code is unavailable to other assemblies.</span></span> <span data-ttu-id="aecf2-148">Un método que se declara **virtuales** y **interno** (**Overloads Overridable Friend** en Visual Basic) puede reemplazar la entrada vtable de la clase primaria y puede utilizarse solo desde dentro del mismo ensamblado porque es interno.</span><span class="sxs-lookup"><span data-stu-id="aecf2-148">A method that is declared **virtual** and **internal** (**Overloads Overridable Friend** in Visual Basic) can override the parent class's vtable entry and can be used only from within the same assembly because it is internal.</span></span> <span data-ttu-id="aecf2-149">Sin embargo, la accesibilidad para invalidar se determina por la **virtuales** (palabra clave) y esto se puede invalidar desde otro ensamblado siempre que ese código tenga acceso a la propia clase.</span><span class="sxs-lookup"><span data-stu-id="aecf2-149">However, the accessibility for overriding is determined by the **virtual** keyword, and this can be overridden from another assembly as long as that code has access to the class itself.</span></span> <span data-ttu-id="aecf2-150">Si la posibilidad de una invalidación supone un problema, utilice la seguridad declarativa para solucionarlo o quite el **virtuales** palabra clave, si no es estrictamente necesaria.</span><span class="sxs-lookup"><span data-stu-id="aecf2-150">If the possibility of an override presents a problem, use declarative security to fix it, or remove the **virtual** keyword if it is not strictly required.</span></span>  
  
 <span data-ttu-id="aecf2-151">Tenga en cuenta que aunque un compilador de lenguaje impida estas invalidaciones con un error de compilación, el código escrito con otros compiladores podría realizar la invalidación.</span><span class="sxs-lookup"><span data-stu-id="aecf2-151">Note that even if a language compiler prevents these overrides with a compilation error, it is possible for code written with other compilers to override.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aecf2-152">Vea también</span><span class="sxs-lookup"><span data-stu-id="aecf2-152">See Also</span></span>  
 [<span data-ttu-id="aecf2-153">Instrucciones de codificación segura</span><span class="sxs-lookup"><span data-stu-id="aecf2-153">Secure Coding Guidelines</span></span>](../../../docs/standard/security/secure-coding-guidelines.md)
