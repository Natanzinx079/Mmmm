-- NATAN DEAD REAILS | VISUAL HUB v0.2.9
-- Feito do zero | Compatível com celular (Delta Executor)

-- Carregar biblioteca de UI moderna
local Library = loadstring(game:HttpGet("https://raw.githubusercontent.com/xHeptc/Kavo-UI-Library/main/source.lua"))()
local Window = Library.CreateLib("Natan Dead Reails | v0.2.9", "Midnight")

-- ABA VISUAL
local Visual = Window:NewTab("Visual")
local Section = Visual:NewSection("Funções Visuais")

-- Função Unlock Mouse
Section:NewToggle("Unlock Mouse", "Desbloqueia o cursor do mouse.", function(state)
    if state then
        local UIS = game:GetService("UserInputService")
        UIS.MouseIconEnabled = true
        UIS.OverrideMouseIconBehavior = Enum.OverrideMouseIconBehavior.ForceShow
    end
end)

-- Função Unlock Camera
Section:NewToggle("Unlock Camera", "Desbloqueia o controle da câmera.", function(state)
    if state then
        local player = game.Players.LocalPlayer
        if player then
            player.CameraMode = Enum.CameraMode.Classic
        end
    end
end)

-- Função Remove Fog
Section:NewToggle("Remove Fog", "Remove toda a neblina do mapa.", function(state)
    if state then
        local lighting = game:GetService("Lighting")
        lighting.FogEnd = 1000000
        lighting.FogStart = 0
    end
end)

-- Função Full Bright
Section:NewToggle("Full Bright", "Ilumina o ambiente ao máximo.", function(state)
    if state then
        local lighting = game:GetService("Lighting")
        lighting.Brightness = 2
        lighting.ClockTime = 14
        lighting.GlobalShadows = false
        lighting.FogEnd = 1000000
    end
end)
