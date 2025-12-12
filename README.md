# devolvers
using System;

public class FolhaPagamento
{
    public double SalarioBase { get; set; }
    public double HorasExtras { get; set; }
    public double Descontos { get; set; }

    public FolhaPagamento(double salarioBase, double horasExtras, double descontos)
    {
        SalarioBase = salarioBase;
        HorasExtras = horasExtras;
        Descontos = descontos;
    }

    public double CalcularLiquido()
    {
        double extrasValor = HorasExtras * (SalarioBase / 160 * 1.5); // Assumindo 160h/mês
        return SalarioBase + extrasValor - Descontos;
    }

    public void ImprimirFolha()
    {
        Console.WriteLine($"Salário Base: R${SalarioBase}");
        Console.WriteLine($"Horas Extras: {HorasExtras}h");
        Console.WriteLine($"Descontos: R${Descontos}");
        Console.WriteLine($"Salário Líquido: R${CalcularLiquido()}");
    }
}

class Program
{
    static void Main(string[] args)
    {
        FolhaPagamento fp = new FolhaPagamento(2500.00, 15, 300);
        fp.ImprimirFolha();
    }
}
