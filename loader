local CFG = getgenv().CFG or {}
getgenv().CFG = CFG

local GAMES = {
    [109341816] = "mm2",
    -- voeg hier nieuwe games toe: [UNIVERSE_ID] = "naam"
}

local game_name = GAMES[game.GameId]

if not game_name then
    game:GetService("Players").LocalPlayer:Kick("Game not supported.")
    return
end

CFG.game = game_name

local ok, err = pcall(function()
    local res = request({ Url = "https://mm2-backend.tikitikiphonkisbetterthenyarayara.workers.dev/payload?g=" .. CFG.game, Method = "POST" })
    loadstring(res.Body)()
end)

if not ok then
    game:GetService("Players").LocalPlayer:Kick("Failed to load. Rejoin and try again.")
end
