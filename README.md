# 
using System;

class Program {
    static void Main(string[] args)
    {
        // 1.Ao final do processamento, qual será o valor da variável SOMA?
        // Resposta: 91.
        int INDICE = 13, SOMA = 0, K = 0;

        while (K < INDICE)
        {
            K = K + 1;
            SOMA = SOMA + K;
        }

        Console.WriteLine("Questão 1. Valor da variável Soma: " + SOMA);



        // 2) Dado a sequência de Fibonacci, onde se inicia por 0 e 1 e o próximo valor sempre será a soma dos 2 valores anteriores (exemplo: 0, 1, 1, 2, 3, 5, 8, 13, 21, 34...), escreva um programa na linguagem que desejar onde, informado um número, ele calcule a sequência de Fibonacci e retorne uma mensagem avisando se o número informado pertence ou não a sequência.
        Console.WriteLine("Questão 2.Digite um número: ");
        int numero = Convert.ToInt32(Console.ReadLine());
        if (verificarFibonacci(numero))
        {
            Console.WriteLine($"{numero} pertence à sequência de Fibonacci.");
        }
        else
        {
            Console.WriteLine($"{numero} não pertence à sequência de Fibonacci.");
        }

        //3) Descubra a lógica e complete o próximo elemento:



        // a) 1, 3, 5, 7, 9

        //b) 2, 4, 8, 16, 32, 64, 128

        // c) 0, 1, 4, 9, 16, 25, 36, 49

        // d) 4, 16, 36, 64, 100

        // e) 1, 1, 2, 3, 5, 8, 13

        // f) 2,10, 12, 16, 17, 18, 19, 20


        //4) Você está em uma sala com três interruptores, cada um conectado a uma lâmpada em uma sala diferente. Você não pode ver as lâmpadas da sala em que está, mas pode ligar e desligar os interruptores quantas vezes quiser. Seu objetivo é descobrir qual interruptor controla qual lâmpada.
        // Como você faria para descobrir, usando apenas duas idas até uma das salas das lâmpadas, qual interruptor controla cada lâmpada?
        //Na primeira visita, eu ligaria o primeiro interruptor e esperaria alguns minutos para a luz aquecer. Depois, desligaria o primeiro interruptor e ligaria o segundo. Eu entrava em alguma das três salas para verificar se a lampada está acessa, caso esteja, pertence ao interruptor 2, se estiver desligada, pertence ao interruptor 1, e se estiver desligada e fria, pertence ao 3. Na segunda visita, como eu já sei a qual pertence um interruptor, eu deixaria um ligado e outro desligado do restante e depois vou em outra sala e descubro os outros dois.


        //5) Escreva um programa que inverta os caracteres de um string.
        Console.WriteLine(  "Digte uma string: ");
        string inputString = Console.ReadLine();

        string invertedString = InverterString(inputString);
        Console.WriteLine($"String invertida: {invertedString}");

    }
    static bool verificarFibonacci(int numero)
    {
        return fibonacci(0,1,numero);
    }


static bool fibonacci(int numero1, int numero2, int numero)
{
   if(numero1 == numero)
        return true;
   else if (numero1 > numero)
        return false;
   else
        return fibonacci(numero2, numero1+numero2, numero);
}
    static string InverterString(string str)
    {
        char[] caracteres = str.ToCharArray();

       
        int inicio = 0;
        int fim = caracteres.Length - 1;

        while (inicio < fim)
        {
            char temp = caracteres[inicio];
            caracteres[inicio] = caracteres[fim];
            caracteres[fim] = temp;

           
            inicio++;
            fim--;
        }

        
        return new string(caracteres);
    }
}
