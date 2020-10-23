---
title: API no admitidas en .NET Core y .NET 5+
titleSuffix: ''
description: Obtenga información sobre qué API de .NET siempre inician una excepción en .NET Core y .NET 5.0 y versiones posteriores.
ms.date: 10/13/2020
ms.openlocfilehash: 0164ebff51de82d548a02f9fde754c1052a9c2b5
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "92159344"
---
# <a name="apis-that-always-throw-exceptions-on-net-core-and-net-5"></a><span data-ttu-id="b9c6e-103">API que siempre inician excepciones en .NET Core y .NET 5+</span><span class="sxs-lookup"><span data-stu-id="b9c6e-103">APIs that always throw exceptions on .NET Core and .NET 5+</span></span>

<span data-ttu-id="b9c6e-104">Las API siguientes siempre iniciarán una excepción <xref:System.PlatformNotSupportedException> en .NET 5.0 y versiones posteriores (incluidas todas las versiones de .NET Core) en todas las plataformas, o bien en un subconjunto de estas.</span><span class="sxs-lookup"><span data-stu-id="b9c6e-104">The following APIs will always throw a <xref:System.PlatformNotSupportedException> on .NET 5.0 and later versions (including all versions of .NET Core) on all or a subset of platforms.</span></span>

<span data-ttu-id="b9c6e-105">En este artículo, las API afectadas se organizan por espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="b9c6e-105">This article organizes the affected APIs by namespace.</span></span>

> [!NOTE]
>
> - <span data-ttu-id="b9c6e-106">Este artículo sigue en desarrollo.</span><span class="sxs-lookup"><span data-stu-id="b9c6e-106">This article is a work-in-progress.</span></span> <span data-ttu-id="b9c6e-107">No es una lista completa de las API que inician excepciones en .NET 5+.</span><span class="sxs-lookup"><span data-stu-id="b9c6e-107">It is not a complete list of APIs that throw exceptions on .NET 5+.</span></span>
> - <span data-ttu-id="b9c6e-108">En este artículo no se incluyen las implementaciones de interfaz explícitas para la serialización binaria que inician excepciones en .NET 5+.</span><span class="sxs-lookup"><span data-stu-id="b9c6e-108">This article does not include the explicit interface implementations for binary serialization that throw on .NET 5+.</span></span> <span data-ttu-id="b9c6e-109">Para obtener más información, vea [Serialización binaria en .NET Core](../../standard/serialization/binary-serialization.md#net-core).</span><span class="sxs-lookup"><span data-stu-id="b9c6e-109">For more information, see [Binary serialization in .NET Core](../../standard/serialization/binary-serialization.md#net-core).</span></span>

## <a name="system"></a><span data-ttu-id="b9c6e-110">Sistema</span><span class="sxs-lookup"><span data-stu-id="b9c6e-110">System</span></span>

| <span data-ttu-id="b9c6e-111">Member</span><span class="sxs-lookup"><span data-stu-id="b9c6e-111">Member</span></span> | <span data-ttu-id="b9c6e-112">Plataformas en las que se produce</span><span class="sxs-lookup"><span data-stu-id="b9c6e-112">Platforms that throw</span></span> |
| - | - |
| <xref:System.AppDomain.CreateDomain%2A?displayProperty=nameWithType> | <span data-ttu-id="b9c6e-113">Todas</span><span class="sxs-lookup"><span data-stu-id="b9c6e-113">All</span></span> |
| <xref:System.AppDomain.ExecuteAssembly(System.String,System.String[],System.Byte[],System.Configuration.Assemblies.AssemblyHashAlgorithm)?displayProperty=nameWithType> | <span data-ttu-id="b9c6e-114">Todas</span><span class="sxs-lookup"><span data-stu-id="b9c6e-114">All</span></span> |
| <xref:System.Console.CapsLock?displayProperty=nameWithType> | <span data-ttu-id="b9c6e-115">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="b9c6e-115">Linux and macOS</span></span> |
| <xref:System.Console.NumberLock?displayProperty=nameWithType> | <span data-ttu-id="b9c6e-116">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="b9c6e-116">Linux and macOS</span></span> |
| <xref:System.Delegate.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="b9c6e-117">Todas</span><span class="sxs-lookup"><span data-stu-id="b9c6e-117">All</span></span> |
| <xref:System.Exception.SerializeObjectState?displayProperty=nameWithType> | <span data-ttu-id="b9c6e-118">Todas</span><span class="sxs-lookup"><span data-stu-id="b9c6e-118">All</span></span> |
| <xref:System.MarshalByRefObject.GetLifetimeService?displayProperty=nameWithType> | <span data-ttu-id="b9c6e-119">Todas</span><span class="sxs-lookup"><span data-stu-id="b9c6e-119">All</span></span> |
| <xref:System.MarshalByRefObject.InitializeLifetimeService?displayProperty=nameWithType> | <span data-ttu-id="b9c6e-120">Todas</span><span class="sxs-lookup"><span data-stu-id="b9c6e-120">All</span></span> |
| <xref:System.OperatingSystem.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="b9c6e-121">Todas</span><span class="sxs-lookup"><span data-stu-id="b9c6e-121">All</span></span> |
| <xref:System.Type.ReflectionOnlyGetType(System.String,System.Boolean,System.Boolean)?displayProperty=nameWithType> | <span data-ttu-id="b9c6e-122">Todas</span><span class="sxs-lookup"><span data-stu-id="b9c6e-122">All</span></span> |

## <a name="systemcodedomcompiler"></a><span data-ttu-id="b9c6e-123">System.CodeDom.Compiler</span><span class="sxs-lookup"><span data-stu-id="b9c6e-123">System.CodeDom.Compiler</span></span>

| <span data-ttu-id="b9c6e-124">Member</span><span class="sxs-lookup"><span data-stu-id="b9c6e-124">Member</span></span> | <span data-ttu-id="b9c6e-125">Plataformas en las que se produce</span><span class="sxs-lookup"><span data-stu-id="b9c6e-125">Platforms that throw</span></span> |
| - | - |
| <xref:System.CodeDom.Compiler.CodeDomProvider.CompileAssemblyFromDom%2A?displayProperty=nameWithType> | <span data-ttu-id="b9c6e-126">Todas</span><span class="sxs-lookup"><span data-stu-id="b9c6e-126">All</span></span> |
| <xref:System.CodeDom.Compiler.CodeDomProvider.CompileAssemblyFromFile%2A?displayProperty=nameWithType> | <span data-ttu-id="b9c6e-127">Todas</span><span class="sxs-lookup"><span data-stu-id="b9c6e-127">All</span></span> |
| <xref:System.CodeDom.Compiler.CodeDomProvider.CompileAssemblyFromSource%2A?displayProperty=nameWithType> | <span data-ttu-id="b9c6e-128">Todas</span><span class="sxs-lookup"><span data-stu-id="b9c6e-128">All</span></span> |

## <a name="systemcollectionsspecialized"></a><span data-ttu-id="b9c6e-129">System.Collections.Specialized</span><span class="sxs-lookup"><span data-stu-id="b9c6e-129">System.Collections.Specialized</span></span>

| <span data-ttu-id="b9c6e-130">Member</span><span class="sxs-lookup"><span data-stu-id="b9c6e-130">Member</span></span> | <span data-ttu-id="b9c6e-131">Plataformas en las que se produce</span><span class="sxs-lookup"><span data-stu-id="b9c6e-131">Platforms that throw</span></span> |
| - | - |
| <xref:System.Collections.Specialized.NameObjectCollectionBase.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="b9c6e-132">Todas</span><span class="sxs-lookup"><span data-stu-id="b9c6e-132">All</span></span> |
| <xref:System.Collections.Specialized.NameObjectCollectionBase.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="b9c6e-133">Todas</span><span class="sxs-lookup"><span data-stu-id="b9c6e-133">All</span></span> |
| <xref:System.Collections.Specialized.NameObjectCollectionBase.OnDeserialization(System.Object)?displayProperty=nameWithType> | <span data-ttu-id="b9c6e-134">Todas</span><span class="sxs-lookup"><span data-stu-id="b9c6e-134">All</span></span> |

## <a name="systemconfiguration"></a><span data-ttu-id="b9c6e-135">System.Configuration</span><span class="sxs-lookup"><span data-stu-id="b9c6e-135">System.Configuration</span></span>

| <span data-ttu-id="b9c6e-136">Member</span><span class="sxs-lookup"><span data-stu-id="b9c6e-136">Member</span></span> | <span data-ttu-id="b9c6e-137">Plataformas en las que se produce</span><span class="sxs-lookup"><span data-stu-id="b9c6e-137">Platforms that throw</span></span> |
| - | - |
| <span data-ttu-id="b9c6e-138"><xref:System.Configuration.RsaProtectedConfigurationProvider?displayProperty=nameWithType> (todos los miembros)</span><span class="sxs-lookup"><span data-stu-id="b9c6e-138"><xref:System.Configuration.RsaProtectedConfigurationProvider?displayProperty=nameWithType> (all members)</span></span> | <span data-ttu-id="b9c6e-139">Todas</span><span class="sxs-lookup"><span data-stu-id="b9c6e-139">All</span></span> |

## <a name="systemconsole"></a><span data-ttu-id="b9c6e-140">System.Console</span><span class="sxs-lookup"><span data-stu-id="b9c6e-140">System.Console</span></span>

| <span data-ttu-id="b9c6e-141">Member</span><span class="sxs-lookup"><span data-stu-id="b9c6e-141">Member</span></span> | <span data-ttu-id="b9c6e-142">Plataformas en las que se produce</span><span class="sxs-lookup"><span data-stu-id="b9c6e-142">Platforms that throw</span></span> |
| - | - |
| <xref:System.Console.Beep?displayProperty=nameWithType> | <span data-ttu-id="b9c6e-143">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="b9c6e-143">Linux and macOS</span></span> |
| <span data-ttu-id="b9c6e-144"><xref:System.Console.BufferHeight?displayProperty=nameWithType> (solo Establecer)</span><span class="sxs-lookup"><span data-stu-id="b9c6e-144"><xref:System.Console.BufferHeight?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="b9c6e-145">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="b9c6e-145">Linux and macOS</span></span> |
| <span data-ttu-id="b9c6e-146"><xref:System.Console.BufferWidth?displayProperty=nameWithType> (solo Establecer)</span><span class="sxs-lookup"><span data-stu-id="b9c6e-146"><xref:System.Console.BufferWidth?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="b9c6e-147">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="b9c6e-147">Linux and macOS</span></span> |
| <span data-ttu-id="b9c6e-148"><xref:System.Console.CursorSize?displayProperty=nameWithType> (solo Establecer)</span><span class="sxs-lookup"><span data-stu-id="b9c6e-148"><xref:System.Console.CursorSize?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="b9c6e-149">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="b9c6e-149">Linux and macOS</span></span> |
| <span data-ttu-id="b9c6e-150"><xref:System.Console.CursorVisible?displayProperty=nameWithType> (solo Obtener)</span><span class="sxs-lookup"><span data-stu-id="b9c6e-150"><xref:System.Console.CursorVisible?displayProperty=nameWithType> (get only)</span></span> | <span data-ttu-id="b9c6e-151">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="b9c6e-151">Linux and macOS</span></span> |
| <xref:System.Console.MoveBufferArea%2A?displayProperty=nameWithType> | <span data-ttu-id="b9c6e-152">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="b9c6e-152">Linux and macOS</span></span> |
| <xref:System.Console.SetWindowPosition%2A?displayProperty=nameWithType> | <span data-ttu-id="b9c6e-153">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="b9c6e-153">Linux and macOS</span></span> |
| <xref:System.Console.SetWindowSize%2A?displayProperty=nameWithType> | <span data-ttu-id="b9c6e-154">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="b9c6e-154">Linux and macOS</span></span> |
| <span data-ttu-id="b9c6e-155"><xref:System.Console.Title?displayProperty=nameWithType> (solo Obtener)</span><span class="sxs-lookup"><span data-stu-id="b9c6e-155"><xref:System.Console.Title?displayProperty=nameWithType> (get only)</span></span> | <span data-ttu-id="b9c6e-156">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="b9c6e-156">Linux and macOS</span></span> |
| <span data-ttu-id="b9c6e-157"><xref:System.Console.WindowHeight?displayProperty=nameWithType> (solo Establecer)</span><span class="sxs-lookup"><span data-stu-id="b9c6e-157"><xref:System.Console.WindowHeight?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="b9c6e-158">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="b9c6e-158">Linux and macOS</span></span> |
| <span data-ttu-id="b9c6e-159"><xref:System.Console.WindowLeft?displayProperty=nameWithType> (solo Establecer)</span><span class="sxs-lookup"><span data-stu-id="b9c6e-159"><xref:System.Console.WindowLeft?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="b9c6e-160">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="b9c6e-160">Linux and macOS</span></span> |
| <span data-ttu-id="b9c6e-161"><xref:System.Console.WindowTop?displayProperty=nameWithType> (solo Establecer)</span><span class="sxs-lookup"><span data-stu-id="b9c6e-161"><xref:System.Console.WindowTop?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="b9c6e-162">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="b9c6e-162">Linux and macOS</span></span> |
| <span data-ttu-id="b9c6e-163"><xref:System.Console.WindowWidth?displayProperty=nameWithType> (solo Establecer)</span><span class="sxs-lookup"><span data-stu-id="b9c6e-163"><xref:System.Console.WindowWidth?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="b9c6e-164">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="b9c6e-164">Linux and macOS</span></span> |

## <a name="systemdatacommon"></a><span data-ttu-id="b9c6e-165">System.Data.Common</span><span class="sxs-lookup"><span data-stu-id="b9c6e-165">System.Data.Common</span></span>

| <span data-ttu-id="b9c6e-166">Member</span><span class="sxs-lookup"><span data-stu-id="b9c6e-166">Member</span></span> | <span data-ttu-id="b9c6e-167">Plataformas en las que se produce</span><span class="sxs-lookup"><span data-stu-id="b9c6e-167">Platforms that throw</span></span> |
| - | - |
| <span data-ttu-id="b9c6e-168"><xref:System.Data.Common.DbDataReader.GetSchemaTable%2A?displayProperty=nameWithType> (genera <xref:System.NotSupportedException>)</span><span class="sxs-lookup"><span data-stu-id="b9c6e-168"><xref:System.Data.Common.DbDataReader.GetSchemaTable%2A?displayProperty=nameWithType> (throws <xref:System.NotSupportedException>)</span></span> | <span data-ttu-id="b9c6e-169">Todas</span><span class="sxs-lookup"><span data-stu-id="b9c6e-169">All</span></span> |

## <a name="systemdiagnosticsprocess"></a><span data-ttu-id="b9c6e-170">System.Diagnostics.Process</span><span class="sxs-lookup"><span data-stu-id="b9c6e-170">System.Diagnostics.Process</span></span>

| <span data-ttu-id="b9c6e-171">Member</span><span class="sxs-lookup"><span data-stu-id="b9c6e-171">Member</span></span> | <span data-ttu-id="b9c6e-172">Plataformas en las que se produce</span><span class="sxs-lookup"><span data-stu-id="b9c6e-172">Platforms that throw</span></span> |
| - | - |
| <span data-ttu-id="b9c6e-173"><xref:System.Diagnostics.Process.MaxWorkingSet?displayProperty=nameWithType> (solo Establecer)</span><span class="sxs-lookup"><span data-stu-id="b9c6e-173"><xref:System.Diagnostics.Process.MaxWorkingSet?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="b9c6e-174">Linux</span><span class="sxs-lookup"><span data-stu-id="b9c6e-174">Linux</span></span> |
| <span data-ttu-id="b9c6e-175"><xref:System.Diagnostics.Process.MinWorkingSet?displayProperty=nameWithType> (solo Establecer)</span><span class="sxs-lookup"><span data-stu-id="b9c6e-175"><xref:System.Diagnostics.Process.MinWorkingSet?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="b9c6e-176">Linux</span><span class="sxs-lookup"><span data-stu-id="b9c6e-176">Linux</span></span> |
| <xref:System.Diagnostics.Process.ProcessorAffinity?displayProperty=nameWithType> | <span data-ttu-id="b9c6e-177">macOS</span><span class="sxs-lookup"><span data-stu-id="b9c6e-177">macOS</span></span> |
| <xref:System.Diagnostics.Process.MainWindowHandle?displayProperty=nameWithType> | <span data-ttu-id="b9c6e-178">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="b9c6e-178">Linux and macOS</span></span> |
| <xref:System.Diagnostics.Process.Start%2A?displayProperty=nameWithType> | <span data-ttu-id="b9c6e-179">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="b9c6e-179">Linux and macOS</span></span> |
| <xref:System.Diagnostics.ProcessStartInfo.UserName?displayProperty=nameWithType> | <span data-ttu-id="b9c6e-180">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="b9c6e-180">Linux and macOS</span></span> |
| <xref:System.Diagnostics.ProcessStartInfo.PasswordInClearText?displayProperty=nameWithType> | <span data-ttu-id="b9c6e-181">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="b9c6e-181">Linux and macOS</span></span> |
| <xref:System.Diagnostics.ProcessStartInfo.Domain?displayProperty=nameWithType> | <span data-ttu-id="b9c6e-182">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="b9c6e-182">Linux and macOS</span></span> |
| <xref:System.Diagnostics.ProcessStartInfo.LoadUserProfile?displayProperty=nameWithType> | <span data-ttu-id="b9c6e-183">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="b9c6e-183">Linux and macOS</span></span> |
| <span data-ttu-id="b9c6e-184"><xref:System.Diagnostics.ProcessThread.BasePriority?displayProperty=nameWithType> (solo Establecer)</span><span class="sxs-lookup"><span data-stu-id="b9c6e-184"><xref:System.Diagnostics.ProcessThread.BasePriority?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="b9c6e-185">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="b9c6e-185">Linux and macOS</span></span> |
| <span data-ttu-id="b9c6e-186"><xref:System.Diagnostics.ProcessThread.BasePriority?displayProperty=nameWithType> (solo Obtener)</span><span class="sxs-lookup"><span data-stu-id="b9c6e-186"><xref:System.Diagnostics.ProcessThread.BasePriority?displayProperty=nameWithType> (get only)</span></span> | <span data-ttu-id="b9c6e-187">macOS</span><span class="sxs-lookup"><span data-stu-id="b9c6e-187">macOS</span></span> |
| <span data-ttu-id="b9c6e-188"><xref:System.Diagnostics.ProcessThread.ProcessorAffinity?displayProperty=nameWithType> (solo Establecer)</span><span class="sxs-lookup"><span data-stu-id="b9c6e-188"><xref:System.Diagnostics.ProcessThread.ProcessorAffinity?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="b9c6e-189">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="b9c6e-189">Linux and macOS</span></span> |

## <a name="systemio"></a><span data-ttu-id="b9c6e-190">System.IO</span><span class="sxs-lookup"><span data-stu-id="b9c6e-190">System.IO</span></span>

| <span data-ttu-id="b9c6e-191">Member</span><span class="sxs-lookup"><span data-stu-id="b9c6e-191">Member</span></span> | <span data-ttu-id="b9c6e-192">Plataformas en las que se produce</span><span class="sxs-lookup"><span data-stu-id="b9c6e-192">Platforms that throw</span></span> |
| - | - |
| <xref:System.IO.FileSystemInfo.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="b9c6e-193">Todas</span><span class="sxs-lookup"><span data-stu-id="b9c6e-193">All</span></span> |
| <xref:System.IO.FileSystemInfo.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="b9c6e-194">Todas</span><span class="sxs-lookup"><span data-stu-id="b9c6e-194">All</span></span> |

## <a name="systemiopipes"></a><span data-ttu-id="b9c6e-195">System.IO.Pipes</span><span class="sxs-lookup"><span data-stu-id="b9c6e-195">System.IO.Pipes</span></span>

| <span data-ttu-id="b9c6e-196">Member</span><span class="sxs-lookup"><span data-stu-id="b9c6e-196">Member</span></span> | <span data-ttu-id="b9c6e-197">Plataformas en las que se produce</span><span class="sxs-lookup"><span data-stu-id="b9c6e-197">Platforms that throw</span></span> |
| - | - |
| <xref:System.IO.Pipes.NamedPipeClientStream.NumberOfServerInstances?displayProperty=nameWithType> | <span data-ttu-id="b9c6e-198">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="b9c6e-198">Linux and macOS</span></span> |
| <xref:System.IO.Pipes.NamedPipeServerStream.GetImpersonationUserName?displayProperty=nameWithType> | <span data-ttu-id="b9c6e-199">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="b9c6e-199">Linux and macOS</span></span> |
| <xref:System.IO.Pipes.PipeStream.InBufferSize?displayProperty=nameWithType> | <span data-ttu-id="b9c6e-200">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="b9c6e-200">Linux and macOS</span></span> |
| <xref:System.IO.Pipes.PipeStream.OutBufferSize?displayProperty=nameWithType> | <span data-ttu-id="b9c6e-201">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="b9c6e-201">Linux and macOS</span></span> |
| <span data-ttu-id="b9c6e-202"><xref:System.IO.Pipes.PipeStream.ReadMode?displayProperty=nameWithType> (solo Establecer)</span><span class="sxs-lookup"><span data-stu-id="b9c6e-202"><xref:System.IO.Pipes.PipeStream.ReadMode?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="b9c6e-203">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="b9c6e-203">Linux and macOS</span></span> |
| <xref:System.IO.Pipes.PipeStream.WaitForPipeDrain?displayProperty=nameWithType> | <span data-ttu-id="b9c6e-204">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="b9c6e-204">Linux and macOS</span></span> |

## <a name="systemmedia"></a><span data-ttu-id="b9c6e-205">System.Media</span><span class="sxs-lookup"><span data-stu-id="b9c6e-205">System.Media</span></span>

| <span data-ttu-id="b9c6e-206">Member</span><span class="sxs-lookup"><span data-stu-id="b9c6e-206">Member</span></span> | <span data-ttu-id="b9c6e-207">Plataformas en las que se produce</span><span class="sxs-lookup"><span data-stu-id="b9c6e-207">Platforms that throw</span></span> |
| - | - |
| <xref:System.Media.SoundPlayer.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="b9c6e-208">Todas</span><span class="sxs-lookup"><span data-stu-id="b9c6e-208">All</span></span> |

## <a name="systemnet"></a><span data-ttu-id="b9c6e-209">System.Net</span><span class="sxs-lookup"><span data-stu-id="b9c6e-209">System.Net</span></span>

| <span data-ttu-id="b9c6e-210">Member</span><span class="sxs-lookup"><span data-stu-id="b9c6e-210">Member</span></span> | <span data-ttu-id="b9c6e-211">Plataformas en las que se produce</span><span class="sxs-lookup"><span data-stu-id="b9c6e-211">Platforms that throw</span></span> |
| - | - |
| <xref:System.Net.AuthenticationManager.Authenticate(System.String,System.Net.WebRequest,System.Net.ICredentials)?displayProperty=nameWithType> | <span data-ttu-id="b9c6e-212">Todas</span><span class="sxs-lookup"><span data-stu-id="b9c6e-212">All</span></span> |
| <xref:System.Net.AuthenticationManager.PreAuthenticate(System.Net.WebRequest,System.Net.ICredentials)?displayProperty=nameWithType> | <span data-ttu-id="b9c6e-213">Todas</span><span class="sxs-lookup"><span data-stu-id="b9c6e-213">All</span></span> |
| <xref:System.Net.FileWebRequest.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="b9c6e-214">Todas</span><span class="sxs-lookup"><span data-stu-id="b9c6e-214">All</span></span> |
| <xref:System.Net.FileWebRequest.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="b9c6e-215">Todas</span><span class="sxs-lookup"><span data-stu-id="b9c6e-215">All</span></span> |
| <xref:System.Net.FileWebResponse.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="b9c6e-216">Todas</span><span class="sxs-lookup"><span data-stu-id="b9c6e-216">All</span></span> |
| <xref:System.Net.FileWebResponse.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="b9c6e-217">Todas</span><span class="sxs-lookup"><span data-stu-id="b9c6e-217">All</span></span> |
| <xref:System.Net.HttpWebRequest.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="b9c6e-218">Todas</span><span class="sxs-lookup"><span data-stu-id="b9c6e-218">All</span></span> |
| <xref:System.Net.HttpWebRequest.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="b9c6e-219">Todas</span><span class="sxs-lookup"><span data-stu-id="b9c6e-219">All</span></span> |
| <xref:System.Net.HttpWebResponse.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="b9c6e-220">Todas</span><span class="sxs-lookup"><span data-stu-id="b9c6e-220">All</span></span> |
| <xref:System.Net.HttpWebResponse.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="b9c6e-221">Todas</span><span class="sxs-lookup"><span data-stu-id="b9c6e-221">All</span></span> |
| <xref:System.Net.WebProxy.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="b9c6e-222">Todas</span><span class="sxs-lookup"><span data-stu-id="b9c6e-222">All</span></span> |
| <xref:System.Net.WebProxy.GetDefaultProxy?displayProperty=nameWithType> | <span data-ttu-id="b9c6e-223">Todas</span><span class="sxs-lookup"><span data-stu-id="b9c6e-223">All</span></span> |
| <xref:System.Net.WebProxy.GetObjectData%2A?displayProperty=nameWithType> | <span data-ttu-id="b9c6e-224">Todas</span><span class="sxs-lookup"><span data-stu-id="b9c6e-224">All</span></span> |
| <xref:System.Net.WebRequest.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="b9c6e-225">Todas</span><span class="sxs-lookup"><span data-stu-id="b9c6e-225">All</span></span> |
| <xref:System.Net.WebRequest.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="b9c6e-226">Todas</span><span class="sxs-lookup"><span data-stu-id="b9c6e-226">All</span></span> |
| <xref:System.Net.WebResponse.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="b9c6e-227">Todas</span><span class="sxs-lookup"><span data-stu-id="b9c6e-227">All</span></span> |
| <xref:System.Net.WebResponse.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="b9c6e-228">Todas</span><span class="sxs-lookup"><span data-stu-id="b9c6e-228">All</span></span> |

## <a name="systemnetnetworkinformation"></a><span data-ttu-id="b9c6e-229">System.Net.NetworkInformation</span><span class="sxs-lookup"><span data-stu-id="b9c6e-229">System.Net.NetworkInformation</span></span>

| <span data-ttu-id="b9c6e-230">Member</span><span class="sxs-lookup"><span data-stu-id="b9c6e-230">Member</span></span> | <span data-ttu-id="b9c6e-231">Plataformas en las que se produce</span><span class="sxs-lookup"><span data-stu-id="b9c6e-231">Platforms that throw</span></span> |
| - | - |
| <xref:System.Net.NetworkInformation.Ping.Send%2A?displayProperty=nameWithType> | <span data-ttu-id="b9c6e-232">Windows (UWP)</span><span class="sxs-lookup"><span data-stu-id="b9c6e-232">Windows (UWP)</span></span> |

## <a name="systemnetsockets"></a><span data-ttu-id="b9c6e-233">System.Net.Sockets</span><span class="sxs-lookup"><span data-stu-id="b9c6e-233">System.Net.Sockets</span></span>

| <span data-ttu-id="b9c6e-234">Member</span><span class="sxs-lookup"><span data-stu-id="b9c6e-234">Member</span></span> | <span data-ttu-id="b9c6e-235">Plataformas en las que se produce</span><span class="sxs-lookup"><span data-stu-id="b9c6e-235">Platforms that throw</span></span> |
| - | - |
| <xref:System.Net.Sockets.Socket.%23ctor(System.Net.Sockets.SocketInformation)> | <span data-ttu-id="b9c6e-236">Todas</span><span class="sxs-lookup"><span data-stu-id="b9c6e-236">All</span></span> |
| <xref:System.Net.Sockets.Socket.DuplicateAndClose(System.Int32)?displayProperty=nameWithType> | <span data-ttu-id="b9c6e-237">Todas</span><span class="sxs-lookup"><span data-stu-id="b9c6e-237">All</span></span> |

## <a name="systemnetwebsockets"></a><span data-ttu-id="b9c6e-238">System.Net.WebSockets</span><span class="sxs-lookup"><span data-stu-id="b9c6e-238">System.Net.WebSockets</span></span>

| <span data-ttu-id="b9c6e-239">Member</span><span class="sxs-lookup"><span data-stu-id="b9c6e-239">Member</span></span> | <span data-ttu-id="b9c6e-240">Plataformas en las que se produce</span><span class="sxs-lookup"><span data-stu-id="b9c6e-240">Platforms that throw</span></span> |
| - | - |
| <xref:System.Net.WebSockets.WebSocket.RegisterPrefixes?displayProperty=nameWithType> | <span data-ttu-id="b9c6e-241">Todas</span><span class="sxs-lookup"><span data-stu-id="b9c6e-241">All</span></span> |

## <a name="systemreflection"></a><span data-ttu-id="b9c6e-242">System.Reflection</span><span class="sxs-lookup"><span data-stu-id="b9c6e-242">System.Reflection</span></span>

| <span data-ttu-id="b9c6e-243">Member</span><span class="sxs-lookup"><span data-stu-id="b9c6e-243">Member</span></span> | <span data-ttu-id="b9c6e-244">Plataformas en las que se produce</span><span class="sxs-lookup"><span data-stu-id="b9c6e-244">Platforms that throw</span></span> |
| - | - |
| <xref:System.Reflection.Assembly.ReflectionOnlyLoad%2A?displayProperty=nameWithType> | <span data-ttu-id="b9c6e-245">Todas</span><span class="sxs-lookup"><span data-stu-id="b9c6e-245">All</span></span> |
| <xref:System.Reflection.Assembly.ReflectionOnlyLoadFrom(System.String)?displayProperty=nameWithType> | <span data-ttu-id="b9c6e-246">Todas</span><span class="sxs-lookup"><span data-stu-id="b9c6e-246">All</span></span> |
| <xref:System.Reflection.AssemblyName.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="b9c6e-247">Todas</span><span class="sxs-lookup"><span data-stu-id="b9c6e-247">All</span></span> |
| <xref:System.Reflection.AssemblyName.OnDeserialization(System.Object)?displayProperty=nameWithType> | <span data-ttu-id="b9c6e-248">Todas</span><span class="sxs-lookup"><span data-stu-id="b9c6e-248">All</span></span> |
| <xref:System.Reflection.StrongNameKeyPair.%23ctor(System.String)> | <span data-ttu-id="b9c6e-249">Todas</span><span class="sxs-lookup"><span data-stu-id="b9c6e-249">All</span></span> |
| <xref:System.Reflection.StrongNameKeyPair.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="b9c6e-250">Todas</span><span class="sxs-lookup"><span data-stu-id="b9c6e-250">All</span></span> |
| <xref:System.Reflection.StrongNameKeyPair.PublicKey?displayProperty=nameWithType> | <span data-ttu-id="b9c6e-251">Todas</span><span class="sxs-lookup"><span data-stu-id="b9c6e-251">All</span></span> |

## <a name="systemruntimecompilerservices"></a><span data-ttu-id="b9c6e-252">System.Runtime.CompilerServices</span><span class="sxs-lookup"><span data-stu-id="b9c6e-252">System.Runtime.CompilerServices</span></span>

| <span data-ttu-id="b9c6e-253">Member</span><span class="sxs-lookup"><span data-stu-id="b9c6e-253">Member</span></span> | <span data-ttu-id="b9c6e-254">Plataformas en las que se produce</span><span class="sxs-lookup"><span data-stu-id="b9c6e-254">Platforms that throw</span></span> |
| - | - |
| <xref:System.Runtime.CompilerServices.DebugInfoGenerator.CreatePdbGenerator?displayProperty=nameWithType> | <span data-ttu-id="b9c6e-255">Todas</span><span class="sxs-lookup"><span data-stu-id="b9c6e-255">All</span></span> |

## <a name="systemruntimeinteropservices"></a><span data-ttu-id="b9c6e-256">System.Runtime.InteropServices</span><span class="sxs-lookup"><span data-stu-id="b9c6e-256">System.Runtime.InteropServices</span></span>

| <span data-ttu-id="b9c6e-257">Member</span><span class="sxs-lookup"><span data-stu-id="b9c6e-257">Member</span></span> | <span data-ttu-id="b9c6e-258">Plataformas en las que se produce</span><span class="sxs-lookup"><span data-stu-id="b9c6e-258">Platforms that throw</span></span> |
| - | - |
| <xref:System.Runtime.InteropServices.Marshal.GetIDispatchForObject(System.Object)?displayProperty=nameWithType> | <span data-ttu-id="b9c6e-259">Todas</span><span class="sxs-lookup"><span data-stu-id="b9c6e-259">All</span></span> |
| <xref:System.Runtime.InteropServices.RuntimeEnvironment.SystemConfigurationFile?displayProperty=nameWithType> | <span data-ttu-id="b9c6e-260">Todas</span><span class="sxs-lookup"><span data-stu-id="b9c6e-260">All</span></span> |
| <xref:System.Runtime.InteropServices.RuntimeEnvironment.GetRuntimeInterfaceAsIntPtr(System.Guid,System.Guid)?displayProperty=nameWithType> | <span data-ttu-id="b9c6e-261">Todas</span><span class="sxs-lookup"><span data-stu-id="b9c6e-261">All</span></span> |
| <xref:System.Runtime.InteropServices.RuntimeEnvironment.GetRuntimeInterfaceAsObject(System.Guid,System.Guid)?displayProperty=nameWithType> | <span data-ttu-id="b9c6e-262">Todas</span><span class="sxs-lookup"><span data-stu-id="b9c6e-262">All</span></span> |
| <xref:System.Runtime.InteropServices.WindowsRuntime.WindowsRuntimeMarshal.StringToHString(System.String)?displayProperty=nameWithType> | <span data-ttu-id="b9c6e-263">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="b9c6e-263">Linux and macOS</span></span> |
| <xref:System.Runtime.InteropServices.WindowsRuntime.WindowsRuntimeMarshal.PtrToStringHString(System.IntPtr)?displayProperty=nameWithType> | <span data-ttu-id="b9c6e-264">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="b9c6e-264">Linux and macOS</span></span> |
| <xref:System.Runtime.InteropServices.WindowsRuntime.WindowsRuntimeMarshal.FreeHString(System.IntPtr)?displayProperty=nameWithType> | <span data-ttu-id="b9c6e-265">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="b9c6e-265">Linux and macOS</span></span> |

## <a name="systemruntimeserialization"></a><span data-ttu-id="b9c6e-266">System.Runtime.Serialization</span><span class="sxs-lookup"><span data-stu-id="b9c6e-266">System.Runtime.Serialization</span></span>

| <span data-ttu-id="b9c6e-267">Member</span><span class="sxs-lookup"><span data-stu-id="b9c6e-267">Member</span></span> | <span data-ttu-id="b9c6e-268">Plataformas en las que se produce</span><span class="sxs-lookup"><span data-stu-id="b9c6e-268">Platforms that throw</span></span> |
| - | - |
| <xref:System.Runtime.Serialization.XsdDataContractExporter.Schemas?displayProperty=nameWithType> | <span data-ttu-id="b9c6e-269">Todas</span><span class="sxs-lookup"><span data-stu-id="b9c6e-269">All</span></span> |

## <a name="systemsecurity"></a><span data-ttu-id="b9c6e-270">System.Security</span><span class="sxs-lookup"><span data-stu-id="b9c6e-270">System.Security</span></span>

| <span data-ttu-id="b9c6e-271">Member</span><span class="sxs-lookup"><span data-stu-id="b9c6e-271">Member</span></span> | <span data-ttu-id="b9c6e-272">Plataformas en las que se produce</span><span class="sxs-lookup"><span data-stu-id="b9c6e-272">Platforms that throw</span></span> |
| - | - |
| <xref:System.Security.CodeAccessPermission.Deny?displayProperty=nameWithType> | <span data-ttu-id="b9c6e-273">Todas</span><span class="sxs-lookup"><span data-stu-id="b9c6e-273">All</span></span> |
| <xref:System.Security.CodeAccessPermission.PermitOnly?displayProperty=nameWithType> | <span data-ttu-id="b9c6e-274">Todas</span><span class="sxs-lookup"><span data-stu-id="b9c6e-274">All</span></span> |
| <xref:System.Security.PermissionSet.ConvertPermissionSet(System.String,System.Byte[],System.String)?displayProperty=nameWithType> | <span data-ttu-id="b9c6e-275">Todas</span><span class="sxs-lookup"><span data-stu-id="b9c6e-275">All</span></span> |
| <xref:System.Security.PermissionSet.Deny?displayProperty=nameWithType> | <span data-ttu-id="b9c6e-276">Todas</span><span class="sxs-lookup"><span data-stu-id="b9c6e-276">All</span></span> |
| <xref:System.Security.PermissionSet.PermitOnly?displayProperty=nameWithType> | <span data-ttu-id="b9c6e-277">Todas</span><span class="sxs-lookup"><span data-stu-id="b9c6e-277">All</span></span> |
| <xref:System.Security.SecurityContext.Capture?displayProperty=nameWithType> | <span data-ttu-id="b9c6e-278">Todas</span><span class="sxs-lookup"><span data-stu-id="b9c6e-278">All</span></span> |
| <xref:System.Security.SecurityContext.CreateCopy?displayProperty=nameWithType> | <span data-ttu-id="b9c6e-279">Todas</span><span class="sxs-lookup"><span data-stu-id="b9c6e-279">All</span></span> |
| <xref:System.Security.SecurityContext.Dispose?displayProperty=nameWithType> | <span data-ttu-id="b9c6e-280">Todas</span><span class="sxs-lookup"><span data-stu-id="b9c6e-280">All</span></span> |
| <xref:System.Security.SecurityContext.IsFlowSuppressed?displayProperty=nameWithType> | <span data-ttu-id="b9c6e-281">Todas</span><span class="sxs-lookup"><span data-stu-id="b9c6e-281">All</span></span> |
| <xref:System.Security.SecurityContext.IsWindowsIdentityFlowSuppressed?displayProperty=nameWithType> | <span data-ttu-id="b9c6e-282">Todas</span><span class="sxs-lookup"><span data-stu-id="b9c6e-282">All</span></span> |
| <xref:System.Security.SecurityContext.RestoreFlow?displayProperty=nameWithType> | <span data-ttu-id="b9c6e-283">Todas</span><span class="sxs-lookup"><span data-stu-id="b9c6e-283">All</span></span> |
| <xref:System.Security.SecurityContext.Run(System.Security.SecurityContext,System.Threading.ContextCallback,System.Object)?displayProperty=nameWithType> | <span data-ttu-id="b9c6e-284">Todas</span><span class="sxs-lookup"><span data-stu-id="b9c6e-284">All</span></span> |
| <xref:System.Security.SecurityContext.SuppressFlow?displayProperty=nameWithType> | <span data-ttu-id="b9c6e-285">Todas</span><span class="sxs-lookup"><span data-stu-id="b9c6e-285">All</span></span> |
| <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity?displayProperty=nameWithType> | <span data-ttu-id="b9c6e-286">Todas</span><span class="sxs-lookup"><span data-stu-id="b9c6e-286">All</span></span> |

## <a name="systemsecurityclaims"></a><span data-ttu-id="b9c6e-287">System.Security.Claims</span><span class="sxs-lookup"><span data-stu-id="b9c6e-287">System.Security.Claims</span></span>

| <span data-ttu-id="b9c6e-288">Member</span><span class="sxs-lookup"><span data-stu-id="b9c6e-288">Member</span></span> | <span data-ttu-id="b9c6e-289">Plataformas en las que se produce</span><span class="sxs-lookup"><span data-stu-id="b9c6e-289">Platforms that throw</span></span> |
| - | - |
| <xref:System.Security.Claims.ClaimsPrincipal.%23ctor> | <span data-ttu-id="b9c6e-290">Todas</span><span class="sxs-lookup"><span data-stu-id="b9c6e-290">All</span></span> |
| <xref:System.Security.Claims.ClaimsPrincipal.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="b9c6e-291">Todas</span><span class="sxs-lookup"><span data-stu-id="b9c6e-291">All</span></span> |
| <xref:System.Security.Claims.ClaimsIdentity.%23ctor(System.Runtime.Serialization.SerializationInfo)> | <span data-ttu-id="b9c6e-292">Todas</span><span class="sxs-lookup"><span data-stu-id="b9c6e-292">All</span></span> |
| <xref:System.Security.Claims.ClaimsIdentity.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="b9c6e-293">Todas</span><span class="sxs-lookup"><span data-stu-id="b9c6e-293">All</span></span> |
| <xref:System.Security.Claims.ClaimsIdentity.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="b9c6e-294">Todas</span><span class="sxs-lookup"><span data-stu-id="b9c6e-294">All</span></span> |

## <a name="systemsecuritycryptography"></a><span data-ttu-id="b9c6e-295">System.Security.Cryptography</span><span class="sxs-lookup"><span data-stu-id="b9c6e-295">System.Security.Cryptography</span></span>

| <span data-ttu-id="b9c6e-296">Member</span><span class="sxs-lookup"><span data-stu-id="b9c6e-296">Member</span></span> | <span data-ttu-id="b9c6e-297">Plataformas en las que se produce</span><span class="sxs-lookup"><span data-stu-id="b9c6e-297">Platforms that throw</span></span> |
| - | - |
| <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create(System.String)?displayProperty=nameWithType> | <span data-ttu-id="b9c6e-298">Todas</span><span class="sxs-lookup"><span data-stu-id="b9c6e-298">All</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.%23ctor%2A> | <span data-ttu-id="b9c6e-299">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="b9c6e-299">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.Accessible?displayProperty=nameWithType> | <span data-ttu-id="b9c6e-300">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="b9c6e-300">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.Exportable?displayProperty=nameWithType> | <span data-ttu-id="b9c6e-301">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="b9c6e-301">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.HardwareDevice?displayProperty=nameWithType> | <span data-ttu-id="b9c6e-302">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="b9c6e-302">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.KeyContainerName?displayProperty=nameWithType> | <span data-ttu-id="b9c6e-303">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="b9c6e-303">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.KeyNumber?displayProperty=nameWithType> | <span data-ttu-id="b9c6e-304">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="b9c6e-304">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.MachineKeyStore?displayProperty=nameWithType> | <span data-ttu-id="b9c6e-305">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="b9c6e-305">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.Protected?displayProperty=nameWithType> | <span data-ttu-id="b9c6e-306">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="b9c6e-306">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.ProviderName?displayProperty=nameWithType> | <span data-ttu-id="b9c6e-307">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="b9c6e-307">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.ProviderType?displayProperty=nameWithType> | <span data-ttu-id="b9c6e-308">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="b9c6e-308">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.RandomlyGenerated?displayProperty=nameWithType> | <span data-ttu-id="b9c6e-309">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="b9c6e-309">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.Removable?displayProperty=nameWithType> | <span data-ttu-id="b9c6e-310">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="b9c6e-310">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.UniqueKeyContainerName?displayProperty=nameWithType> | <span data-ttu-id="b9c6e-311">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="b9c6e-311">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.HashAlgorithm.Create?displayProperty=nameWithType> | <span data-ttu-id="b9c6e-312">Todas</span><span class="sxs-lookup"><span data-stu-id="b9c6e-312">All</span></span> |
| <xref:System.Security.Cryptography.HMAC.Create?displayProperty=nameWithType> | <span data-ttu-id="b9c6e-313">Todas</span><span class="sxs-lookup"><span data-stu-id="b9c6e-313">All</span></span> |
| <xref:System.Security.Cryptography.HMAC.Create(System.String)?displayProperty=nameWithType> | <span data-ttu-id="b9c6e-314">Todas</span><span class="sxs-lookup"><span data-stu-id="b9c6e-314">All</span></span> |
| <xref:System.Security.Cryptography.HMAC.HashCore%2A?displayProperty=nameWithType> | <span data-ttu-id="b9c6e-315">Todas</span><span class="sxs-lookup"><span data-stu-id="b9c6e-315">All</span></span> |
| <xref:System.Security.Cryptography.HMAC.HashFinal%2A?displayProperty=nameWithType> | <span data-ttu-id="b9c6e-316">Todas</span><span class="sxs-lookup"><span data-stu-id="b9c6e-316">All</span></span> |
| <xref:System.Security.Cryptography.HMAC.Initialize%2A?displayProperty=nameWithType> | <span data-ttu-id="b9c6e-317">Todas</span><span class="sxs-lookup"><span data-stu-id="b9c6e-317">All</span></span> |
| <xref:System.Security.Cryptography.KeyedHashAlgorithm.Create?displayProperty=nameWithType> | <span data-ttu-id="b9c6e-318">Todas</span><span class="sxs-lookup"><span data-stu-id="b9c6e-318">All</span></span> |
| <xref:System.Security.Cryptography.KeyedHashAlgorithm.Create(System.String)?displayProperty=nameWithType> | <span data-ttu-id="b9c6e-319">Todas</span><span class="sxs-lookup"><span data-stu-id="b9c6e-319">All</span></span> |
| <xref:System.Security.Cryptography.ProtectedData.Protect%2A?displayProperty=nameWithType> | <span data-ttu-id="b9c6e-320">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="b9c6e-320">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.ProtectedData.Unprotect%2A?displayProperty=nameWithType> | <span data-ttu-id="b9c6e-321">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="b9c6e-321">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.RSA.FromXmlString%2A?displayProperty=nameWithType> | <span data-ttu-id="b9c6e-322">Todas</span><span class="sxs-lookup"><span data-stu-id="b9c6e-322">All</span></span> |
| <xref:System.Security.Cryptography.RSA.ToXmlString%2A?displayProperty=nameWithType> | <span data-ttu-id="b9c6e-323">Todas</span><span class="sxs-lookup"><span data-stu-id="b9c6e-323">All</span></span> |
| <xref:System.Security.Cryptography.SymmetricAlgorithm.Create?displayProperty=nameWithType> | <span data-ttu-id="b9c6e-324">Todas</span><span class="sxs-lookup"><span data-stu-id="b9c6e-324">All</span></span> |
| <xref:System.Security.Cryptography.SymmetricAlgorithm.Create(System.String)?displayProperty=nameWithType> | <span data-ttu-id="b9c6e-325">Todas</span><span class="sxs-lookup"><span data-stu-id="b9c6e-325">All</span></span> |

## <a name="systemsecuritycryptographypkcs"></a><span data-ttu-id="b9c6e-326">System.Security.Cryptography.Pkcs</span><span class="sxs-lookup"><span data-stu-id="b9c6e-326">System.Security.Cryptography.Pkcs</span></span>

| <span data-ttu-id="b9c6e-327">Member</span><span class="sxs-lookup"><span data-stu-id="b9c6e-327">Member</span></span> | <span data-ttu-id="b9c6e-328">Plataformas en las que se produce</span><span class="sxs-lookup"><span data-stu-id="b9c6e-328">Platforms that throw</span></span> |
| - | - |
| <xref:System.Security.Cryptography.Pkcs.CmsSigner.%23ctor(System.Security.Cryptography.CspParameters)> | <span data-ttu-id="b9c6e-329">Todas</span><span class="sxs-lookup"><span data-stu-id="b9c6e-329">All</span></span> |
| <xref:System.Security.Cryptography.Pkcs.SignerInfo.ComputeCounterSignature?displayProperty=nameWithType> | <span data-ttu-id="b9c6e-330">Todas</span><span class="sxs-lookup"><span data-stu-id="b9c6e-330">All</span></span> |

## <a name="systemsecuritycryptographyx509certificates"></a><span data-ttu-id="b9c6e-331">System.Security.Cryptography.X509Certificates</span><span class="sxs-lookup"><span data-stu-id="b9c6e-331">System.Security.Cryptography.X509Certificates</span></span>

| <span data-ttu-id="b9c6e-332">Miembro</span><span class="sxs-lookup"><span data-stu-id="b9c6e-332">Member</span></span> | <span data-ttu-id="b9c6e-333">Plataformas en las que se produce</span><span class="sxs-lookup"><span data-stu-id="b9c6e-333">Platforms that throw</span></span> |
| - | - |
| <xref:System.Security.Cryptography.X509Certificates.X509Certificate.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="b9c6e-334">All</span><span class="sxs-lookup"><span data-stu-id="b9c6e-334">All</span></span> |
| <xref:System.Security.Cryptography.X509Certificates.X509Certificate.Import%2A?displayProperty=nameWithType> | <span data-ttu-id="b9c6e-335">Todas</span><span class="sxs-lookup"><span data-stu-id="b9c6e-335">All</span></span> |
| <xref:System.Security.Cryptography.X509Certificates.X509Certificate2.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="b9c6e-336">Todas</span><span class="sxs-lookup"><span data-stu-id="b9c6e-336">All</span></span> |
| <span data-ttu-id="b9c6e-337"><xref:System.Security.Cryptography.X509Certificates.X509Certificate2.PrivateKey?displayProperty=nameWithType> (solo Establecer)</span><span class="sxs-lookup"><span data-stu-id="b9c6e-337"><xref:System.Security.Cryptography.X509Certificates.X509Certificate2.PrivateKey?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="b9c6e-338">Todos</span><span class="sxs-lookup"><span data-stu-id="b9c6e-338">All</span></span> |

## <a name="systemsecurityauthenticationextendedprotection"></a><span data-ttu-id="b9c6e-339">System.Security.Authentication.ExtendedProtection</span><span class="sxs-lookup"><span data-stu-id="b9c6e-339">System.Security.Authentication.ExtendedProtection</span></span>

| <span data-ttu-id="b9c6e-340">Miembro</span><span class="sxs-lookup"><span data-stu-id="b9c6e-340">Member</span></span> | <span data-ttu-id="b9c6e-341">Plataformas en las que se produce</span><span class="sxs-lookup"><span data-stu-id="b9c6e-341">Platforms that throw</span></span> |
| - | - |
| <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="b9c6e-342">Todos</span><span class="sxs-lookup"><span data-stu-id="b9c6e-342">All</span></span> |

## <a name="systemsecuritypolicy"></a><span data-ttu-id="b9c6e-343">System.Security.Policy</span><span class="sxs-lookup"><span data-stu-id="b9c6e-343">System.Security.Policy</span></span>

| <span data-ttu-id="b9c6e-344">Miembro</span><span class="sxs-lookup"><span data-stu-id="b9c6e-344">Member</span></span> | <span data-ttu-id="b9c6e-345">Plataformas en las que se produce</span><span class="sxs-lookup"><span data-stu-id="b9c6e-345">Platforms that throw</span></span> |
| - | - |
| <xref:System.Security.Policy.Hash.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="b9c6e-346">Todos</span><span class="sxs-lookup"><span data-stu-id="b9c6e-346">All</span></span> |

## <a name="systemserviceprocessservicecontroller"></a><span data-ttu-id="b9c6e-347">System.ServiceProcess.ServiceController</span><span class="sxs-lookup"><span data-stu-id="b9c6e-347">System.ServiceProcess.ServiceController</span></span>

| <span data-ttu-id="b9c6e-348">Miembro</span><span class="sxs-lookup"><span data-stu-id="b9c6e-348">Member</span></span> | <span data-ttu-id="b9c6e-349">Plataformas en las que se produce</span><span class="sxs-lookup"><span data-stu-id="b9c6e-349">Platforms that throw</span></span> |
| - | - |
| <xref:System.ServiceProcess.TimeoutException.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="b9c6e-350">Todos</span><span class="sxs-lookup"><span data-stu-id="b9c6e-350">All</span></span> |

## <a name="systemtextregularexpressions"></a><span data-ttu-id="b9c6e-351">System.Text.RegularExpressions</span><span class="sxs-lookup"><span data-stu-id="b9c6e-351">System.Text.RegularExpressions</span></span>

| <span data-ttu-id="b9c6e-352">Miembro</span><span class="sxs-lookup"><span data-stu-id="b9c6e-352">Member</span></span> | <span data-ttu-id="b9c6e-353">Plataformas en las que se produce</span><span class="sxs-lookup"><span data-stu-id="b9c6e-353">Platforms that throw</span></span> |
| - | - |
| <xref:System.Text.RegularExpressions.Regex.CompileToAssembly%2A?displayProperty=nameWithType> | <span data-ttu-id="b9c6e-354">Todos</span><span class="sxs-lookup"><span data-stu-id="b9c6e-354">All</span></span> |

## <a name="systemthreading"></a><span data-ttu-id="b9c6e-355">System.Threading</span><span class="sxs-lookup"><span data-stu-id="b9c6e-355">System.Threading</span></span>

| <span data-ttu-id="b9c6e-356">Miembro</span><span class="sxs-lookup"><span data-stu-id="b9c6e-356">Member</span></span> | <span data-ttu-id="b9c6e-357">Plataformas en las que se produce</span><span class="sxs-lookup"><span data-stu-id="b9c6e-357">Platforms that throw</span></span> |
| - | - |
| <xref:System.Threading.CompressedStack.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="b9c6e-358">All</span><span class="sxs-lookup"><span data-stu-id="b9c6e-358">All</span></span> |
| <xref:System.Threading.ExecutionContext.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="b9c6e-359">Todas</span><span class="sxs-lookup"><span data-stu-id="b9c6e-359">All</span></span> |
| <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> | <span data-ttu-id="b9c6e-360">Todas</span><span class="sxs-lookup"><span data-stu-id="b9c6e-360">All</span></span> |
| <xref:System.Threading.Thread.ResetAbort?displayProperty=nameWithType> | <span data-ttu-id="b9c6e-361">Todas</span><span class="sxs-lookup"><span data-stu-id="b9c6e-361">All</span></span> |
| <xref:System.Threading.Thread.Resume?displayProperty=nameWithType> | <span data-ttu-id="b9c6e-362">Todas</span><span class="sxs-lookup"><span data-stu-id="b9c6e-362">All</span></span> |
| <xref:System.Threading.Thread.Suspend?displayProperty=nameWithType> | <span data-ttu-id="b9c6e-363">Todas</span><span class="sxs-lookup"><span data-stu-id="b9c6e-363">All</span></span> |

## <a name="systemxml"></a><span data-ttu-id="b9c6e-364">System.Xml</span><span class="sxs-lookup"><span data-stu-id="b9c6e-364">System.Xml</span></span>

| <span data-ttu-id="b9c6e-365">Miembro</span><span class="sxs-lookup"><span data-stu-id="b9c6e-365">Member</span></span> | <span data-ttu-id="b9c6e-366">Plataformas en las que se produce</span><span class="sxs-lookup"><span data-stu-id="b9c6e-366">Platforms that throw</span></span> |
| - | - |
| <xref:System.Xml.XmlDictionaryReader.CreateMtomReader(System.Byte[],System.Int32,System.Int32,System.Text.Encoding[],System.String,System.Xml.XmlDictionaryReaderQuotas,System.Int32,System.Xml.OnXmlDictionaryReaderClose)?displayProperty=nameWithType> | <span data-ttu-id="b9c6e-367">All</span><span class="sxs-lookup"><span data-stu-id="b9c6e-367">All</span></span> |
| <xref:System.Xml.XmlDictionaryReader.CreateMtomReader(System.IO.Stream,System.Text.Encoding[],System.String,System.Xml.XmlDictionaryReaderQuotas,System.Int32,System.Xml.OnXmlDictionaryReaderClose)?displayProperty=nameWithType> | <span data-ttu-id="b9c6e-368">Todas</span><span class="sxs-lookup"><span data-stu-id="b9c6e-368">All</span></span> |
| <xref:System.Xml.XmlDictionaryWriter.CreateMtomWriter(System.IO.Stream,System.Text.Encoding,System.Int32,System.String,System.String,System.String,System.Boolean,System.Boolean)?displayProperty=nameWithType> | <span data-ttu-id="b9c6e-369">Todas</span><span class="sxs-lookup"><span data-stu-id="b9c6e-369">All</span></span> |

## <a name="see-also"></a><span data-ttu-id="b9c6e-370">Vea también</span><span class="sxs-lookup"><span data-stu-id="b9c6e-370">See also</span></span>

- [<span data-ttu-id="b9c6e-371">Cambios importantes para la migración desde .NET Framework a .NET Core</span><span class="sxs-lookup"><span data-stu-id="b9c6e-371">Breaking changes for migration from .NET Framework to .NET Core</span></span>](fx-core.md)
- [<span data-ttu-id="b9c6e-372">Serialización binaria en .NET Core</span><span class="sxs-lookup"><span data-stu-id="b9c6e-372">Binary serialization in .NET Core</span></span>](../../standard/serialization/binary-serialization.md#net-core)
- [<span data-ttu-id="b9c6e-373">Analizador de portabilidad de .NET</span><span class="sxs-lookup"><span data-stu-id="b9c6e-373">.NET portability analyzer</span></span>](../../standard/analyzers/portability-analyzer.md)
