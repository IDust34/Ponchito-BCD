# Ponchito-BCD
Código para QUARTUS II

--Sumador con 7 segmentos que sume hasta el 9
library ieee;
use ieee.std_logic_1164.all;
use ieee.std_logic_unsigned.all; -- libreria suma vectores(no se uso pero pa saber)
entity suma is
--Declaracion de los selectores, entradas, salida 
port(
     A: in std_logic_vector (3 downto 0);      --A=BCD
	  c: out std_logic_vector  (6 downto 0)  ); -- Saida
	                                                 
end suma;

architecture cepa of suma is
begin                  --   a b c d e f g
  process (A) begin                        
  if   (A="0000") then --0  1 1 1 1 1 1 0
  c<="1111110";
  elsif(A="0001")then  --1  0 1 1 0 0 0 0
  c<="0110000";
  elsif(A="0010")then  --2  1 1 0 1 1 0 1
  c<="1101101";
  elsif(A="0011")then  --3  1 1 1 1 0 0 1
  c<="1111001";
  elsif(A="0100")then  --4  0 1 1 0 0 1 1
  c<="0110011";
  elsif(A="0101")then  --5  1 0 1 1 0 1 1
  c<="1011011";
  elsif(A="0110")then  --6  1 0 1 1 1 1 1
  c<="1011111";
  elsif(A="0111")then  --7  1 1 1 0 0 0 1
  c<="1110001";
  elsif(A="1000")then  --8  1 1 1 1 1 1 1
  c<="1111111";
  elsif(A="1001")then  --9  1 1 1 1 0 1 1
  c<="1111011";
  else
  c<="0000000";
    end if;
  end process;
end cepa;
