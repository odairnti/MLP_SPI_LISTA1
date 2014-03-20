import javax.swing.JOptionPane;

public class SomaInteiros {

	/**
	 * Método para concatenar e somar os números que estão misturados
	 * Programador: Odair Data...: 20/03/2014 16:09
	 * 
	 * obs: Mestre Jefferson tentei mas não consegui fazer com expressão regular
	 * pois não achei uma forma de usar um delimitador.
	 * 
	 * Pattern pattern = Pattern.compile("[0-9]"); 
	 * Matcher matcher = pattern.matcher("123abc123");
	 * 
	 * no laço ele faz somente dos números 123123
	 */
	public static void main(String[] args) {
		String vValores = null;
		String vSoma = "";
		int vTotal = 0;

		// inserir informação.
		String valor = JOptionPane.showInputDialog(null, "Digite os dados");

		// faz um laço para concatenar somente os números.
		for (int i = 0; i < valor.length(); i++) {
			vValores = Character.toString(valor.charAt(i));

			if (eNumerico(vValores) == true) {
				vSoma += vValores; // concatena
			} else {
				if (vSoma != "") {
					vTotal += Integer.parseInt(vSoma); // soma
				}
				vSoma = ""; // limpa concatenação
			}

		}
		if (vSoma != "") {
			vTotal += Integer.parseInt(vSoma); // soma após sair do laço.
		}

		// mostra soma total geral
		JOptionPane.showMessageDialog(null, "Valor Total é:\n" + vTotal);

	}

	// função que retorna se é um número válido
	public static boolean eNumerico(String vValores) {
		boolean ehNumero = false;
		try {
			Integer.parseInt(vValores);
			ehNumero = true;
		} catch (NumberFormatException ex) {
			ehNumero = false;
		}
		return ehNumero;
	}
}
