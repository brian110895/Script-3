-- Variáveis
local velocidade = 1
local max_velocidade = 100
local min_velocidade = 1

-- Função para desenhar a interface
function love.draw()
    -- Exibir o texto da velocidade atual
    love.graphics.print("Velocidade: " .. velocidade, 20, 20)

    -- Desenhar os botões de aumentar e diminuir
    love.graphics.setColor(0.4, 0.8, 0.4) -- Cor verde para aumentar
    love.graphics.rectangle("fill", 20, 60, 200, 50)
    love.graphics.setColor(1, 1, 1) -- Cor branca para o texto
    love.graphics.print("Aumentar Velocidade", 80, 75)

    love.graphics.setColor(0.8, 0.4, 0.4) -- Cor vermelha para diminuir
    love.graphics.rectangle("fill", 20, 130, 200, 50)
    love.graphics.setColor(1, 1, 1)
    love.graphics.print("Diminuir Velocidade", 80, 145)
end

-- Função para lidar com os cliques do mouse
function love.mousepressed(x, y, button, istouch, presses)
    -- Verificar se o clique foi no botão de aumentar a velocidade
    if button == 1 then
        if x >= 20 and x <= 220 and y >= 60 and y <= 110 then
            if velocidade < max_velocidade then
                velocidade = velocidade + 1
            end
        -- Verificar se o clique foi no botão de diminuir a velocidade
        elseif x >= 20 and x <= 220 and y >= 130 and y <= 180 then
            if velocidade > min_velocidade then
                velocidade = velocidade - 1
            end
        end
    end
end
