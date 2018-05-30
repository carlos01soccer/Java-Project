package GUI;

import java.awt.EventQueue;


import javax.swing.JFrame;
import javax.swing.JLabel;
import javax.swing.JOptionPane;

import java.awt.BorderLayout;
import javax.swing.SwingConstants;
import java.awt.Font;
import java.awt.Color;
import java.awt.SystemColor;
import java.awt.TextField;
import java.awt.Window;

import javax.swing.UIManager;

import Clases.Archivos;

import javax.swing.JTextField;
import javax.swing.JButton;
import java.awt.event.ActionListener;
import java.awt.event.ActionEvent;
import java.awt.event.MouseAdapter;
import java.awt.event.MouseEvent;
import java.awt.Canvas;
import javax.swing.JComboBox;
import javax.swing.JPasswordField;
import javax.swing.JRadioButton;
import javax.swing.ButtonGroup;

public class Menu {
	
	String usuarioNuevo,contraseña,nombre,apellido,decision,codigo,codigoproducto,nombreproducto,costo,cantidad;
	private JFrame frame;
	private JTextField TextoUsuario;
	private JPasswordField TextoContraseña;
	private JTextField TextoNombre;
	private JTextField TextoApellido;
	private final ButtonGroup buttonGroup = new ButtonGroup();
	private JTextField TextoCodigo;
	private JTextField InfoNombre;
	private JTextField InfoApellido;
	private JTextField InfoUsuario;
	private JTextField InfoContra;
	private JTextField codproducto2;
	private JTextField nombproducto2;
	private JTextField costproducto2;
	private JTextField cantproducto2;
	

	/*Arranca la interfaz grafica del programa*/
	public static void main(String[] args) {
		EventQueue.invokeLater(new Runnable() {
			public void run() {
				try {
					Menu window = new Menu();
					window.frame.setVisible(true);
				} catch (Exception e) {
					e.printStackTrace();
				}
			}
		});
	}

	/*Crear la aplicacion*/
	public Menu() {
		initialize();
	}

	/*Inicializar los contenidos de la ventana*/
	private void initialize() {
		 
		frame = new JFrame();
		frame.setForeground(Color.WHITE);
		frame.setBackground(Color.GRAY);
		frame.getContentPane().setBackground(Color.GRAY);
		frame.getContentPane().setForeground(Color.GRAY);
		frame.setBounds(100, 100, 500, 400);
		frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
		frame.getContentPane().setLayout(null);
				
		JLabel Titulo = new JLabel("MAQUINA DISPENSADORA");		
		Titulo.setBackground(Color.RED);
		Titulo.setForeground(Color.YELLOW);
		Titulo.setFont(new Font("Lucida Sans", Font.BOLD, 18));
		Titulo.setHorizontalAlignment(SwingConstants.CENTER);
		Titulo.setBounds(117, 25, 267, 46);
		frame.getContentPane().add(Titulo);
		
		JLabel Usuario = new JLabel("Usuario:");
		Usuario.setBackground(UIManager.getColor("Button.background"));
		Usuario.setForeground(Color.BLACK);
		Usuario.setFont(new Font("Franklin Gothic Book", Font.BOLD, 16));
		Usuario.setHorizontalAlignment(SwingConstants.CENTER);
		Usuario.setBounds(94, 161, 100, 38);
		frame.getContentPane().add(Usuario);
		
		JLabel Contraseña = new JLabel("Contrase\u00F1a:");
		Contraseña.setForeground(Color.BLACK);
		Contraseña.setHorizontalAlignment(SwingConstants.CENTER);
		Contraseña.setFont(new Font("Franklin Gothic Book", Font.BOLD, 16));
		Contraseña.setBounds(104, 202, 100, 38);
		frame.getContentPane().add(Contraseña);
		
		JLabel UsuarioNuevo = new JLabel("Nombre De Usuario:");
		UsuarioNuevo.setVisible(false);
		UsuarioNuevo.setForeground(Color.BLACK);
		UsuarioNuevo.setHorizontalAlignment(SwingConstants.CENTER);
		UsuarioNuevo.setFont(new Font("Franklin Gothic Book", Font.BOLD, 14));
		UsuarioNuevo.setBounds(74, 162, 144, 38);
		frame.getContentPane().add(UsuarioNuevo);
		
		JLabel ContraNueva = new JLabel("Contrase\u00F1a:");
		ContraNueva.setVisible(false);
		ContraNueva.setForeground(Color.BLACK);
		ContraNueva.setFont(new Font("Franklin Gothic Book", Font.BOLD, 16));
		ContraNueva.setHorizontalAlignment(SwingConstants.CENTER);
		ContraNueva.setBounds(84, 198, 140, 46);
		frame.getContentPane().add(ContraNueva);
		
		JLabel RegistroTitulo = new JLabel("REGISTRO DE USUARIO:");
		RegistroTitulo.setVisible(false);
		RegistroTitulo.setForeground(Color.RED);
		RegistroTitulo.setHorizontalAlignment(SwingConstants.CENTER);
		RegistroTitulo.setFont(new Font("Lucida Sans", Font.BOLD, 18));
		RegistroTitulo.setBounds(117, 11, 267, 38);
		frame.getContentPane().add(RegistroTitulo);
		
		JLabel NombreNuevo = new JLabel("Nombre:");
		NombreNuevo.setVisible(false);
		NombreNuevo.setHorizontalAlignment(SwingConstants.CENTER);
		NombreNuevo.setFont(new Font("Franklin Gothic Book", Font.BOLD, 16));
		NombreNuevo.setBounds(74, 91, 144, 28);
		frame.getContentPane().add(NombreNuevo);
		
		JLabel ApellidoNuevo = new JLabel("Apellido:");
		ApellidoNuevo.setVisible(false);
		ApellidoNuevo.setFont(new Font("Franklin Gothic Book", Font.BOLD, 16));
		ApellidoNuevo.setHorizontalAlignment(SwingConstants.CENTER);
		ApellidoNuevo.setBounds(74, 128, 144, 35);
		frame.getContentPane().add(ApellidoNuevo);
		
		JLabel PreguntaUsuarioU = new JLabel("\u00BFUsuario De La U?");
		PreguntaUsuarioU.setForeground(Color.BLACK);
		PreguntaUsuarioU.setVisible(false);
		PreguntaUsuarioU.setFont(new Font("Franklin Gothic Book", Font.BOLD, 14));
		PreguntaUsuarioU.setBounds(74, 238, 144, 46);
		frame.getContentPane().add(PreguntaUsuarioU);
		
		JLabel NombreUsuario = new JLabel("Usuario:");
		NombreUsuario.setHorizontalAlignment(SwingConstants.CENTER);
		NombreUsuario.setVisible(false);
		NombreUsuario.setFont(new Font("Lucida Sans", Font.BOLD, 15));
		NombreUsuario.setBounds(0, 0, 74, 28);
		frame.getContentPane().add(NombreUsuario);
		
		JLabel NombreActivo = new JLabel("");
		NombreActivo.setHorizontalAlignment(SwingConstants.CENTER);
		NombreActivo.setVisible(false);
		NombreActivo.setBounds(60, 0, 89, 28);
		frame.getContentPane().add(NombreActivo);
		
		JLabel MenuPrincipal = new JLabel("Menu Principal");
		MenuPrincipal.setVisible(false);
		MenuPrincipal.setForeground(Color.BLACK);
		MenuPrincipal.setBackground(Color.WHITE);
		MenuPrincipal.setHorizontalAlignment(SwingConstants.CENTER);
		MenuPrincipal.setFont(new Font("Lucida Sans", Font.BOLD, 18));
		MenuPrincipal.setBounds(129, 11, 242, 38);
		frame.getContentPane().add(MenuPrincipal);
		
		JLabel ActualizarDatos = new JLabel("ACTUALIZAR DATOS");
		ActualizarDatos.setForeground(Color.GREEN);
		ActualizarDatos.setFont(new Font("Lucida Sans", Font.BOLD, 16));
		ActualizarDatos.setHorizontalAlignment(SwingConstants.CENTER);
		ActualizarDatos.setVisible(false);
		ActualizarDatos.setBounds(139, 30, 189, 38);
		frame.getContentPane().add(ActualizarDatos);
		
		TextoUsuario = new JTextField();
		TextoUsuario.setBounds(269, 168, 134, 28);
		frame.getContentPane().add(TextoUsuario);
		TextoUsuario.setColumns(10);
		
		TextoContraseña = new JPasswordField();
		TextoContraseña.setBounds(269, 207, 134, 28);
		frame.getContentPane().add(TextoContraseña);
		
		TextoNombre = new JTextField();
		TextoNombre.setVisible(false);
		TextoNombre.setBounds(269, 92, 134, 28);
		frame.getContentPane().add(TextoNombre);
		TextoNombre.setColumns(10);
		
		TextoApellido = new JTextField();
		TextoApellido.setVisible(false);
		TextoApellido.setBounds(269, 131, 134, 26);
		frame.getContentPane().add(TextoApellido);
		TextoApellido.setColumns(10);
		
		
		JButton Salir = new JButton("Salir");
		Salir.setBackground(Color.DARK_GRAY);
		Salir.setForeground(Color.RED);
		Salir.setFont(new Font("Franklin Gothic Book", Font.BOLD, 14));
		Salir.setBounds(346, 304, 128, 46);
		frame.getContentPane().add(Salir);

		
		JButton Ingresar = new JButton("Ingresar");
		Ingresar.setBackground(Color.LIGHT_GRAY);
		Ingresar.setForeground(Color.BLUE);
		Ingresar.setFont(new Font("Franklin Gothic Book", Font.BOLD, 13));
		Ingresar.setBounds(180, 304, 128, 46);
		frame.getContentPane().add(Ingresar);
		
		
		JButton Crear = new JButton("Crear Usuario");
		Crear.setForeground(Color.GREEN);
		Crear.setBackground(Color.DARK_GRAY);
		Crear.setFont(new Font("Franklin Gothic Book", Font.BOLD, 13));
		Crear.setBounds(10, 304, 128, 46);
		frame.getContentPane().add(Crear);
		
		JButton CrearUsuarioBoton = new JButton("Crear Nuevo Usuario");
		CrearUsuarioBoton.setVisible(false);
		CrearUsuarioBoton.setBackground(Color.BLUE);
		CrearUsuarioBoton.setFont(new Font("Franklin Gothic Book", Font.BOLD, 13));
		CrearUsuarioBoton.setBounds(245, 294, 175, 56);
		CrearUsuarioBoton.setForeground(Color.ORANGE);
		frame.getContentPane().add(CrearUsuarioBoton);
		
		JButton VolverMenu = new JButton("Volver al Menu");
		VolverMenu.setBackground(Color.LIGHT_GRAY);
		VolverMenu.setForeground(Color.DARK_GRAY);
		VolverMenu.setVisible(false);
		VolverMenu.setFont(new Font("Franklin Gothic Book", Font.BOLD, 14));
		VolverMenu.setBounds(60, 295, 175, 55);
		frame.getContentPane().add(VolverMenu);
		
		JRadioButton SiRadio = new JRadioButton("SI");
		buttonGroup.add(SiRadio);
		SiRadio.setVisible(false);
		
		JButton Recargar = new JButton("Recargar");
		
		Recargar.setForeground(Color.BLUE);
		Recargar.setFont(new Font("Franklin Gothic Book", Font.BOLD, 13));
		Recargar.setVisible(false);
		Recargar.setBounds(180, 304, 128, 46);
		frame.getContentPane().add(Recargar);
		
		JButton Transferir = new JButton("Transferir");
		Transferir.setForeground(Color.YELLOW);
		Transferir.setFont(new Font("Franklin Gothic Book", Font.BOLD, 13));
		Transferir.setVisible(false);
		Transferir.setBounds(357, 252, 117, 44);
		frame.getContentPane().add(Transferir);
		
		JButton SalirSistema = new JButton("LogOut");
		
		SalirSistema.setForeground(Color.RED);
		SalirSistema.setFont(new Font("Franklin Gothic Book", Font.BOLD, 13));
		SalirSistema.setVisible(false);
		
		SalirSistema.setBounds(357, 304, 117, 46);
		frame.getContentPane().add(SalirSistema);
		
		
		
		JButton Consultar = new JButton("Consultar");
		
		Consultar.setFont(new Font("Franklin Gothic Book", Font.BOLD, 13));
		Consultar.setVisible(false);
		Consultar.setBounds(10, 305, 128, 44);
		frame.getContentPane().add(Consultar);
		
		
		JButton Comprar = new JButton("Comprar");
		Comprar.setForeground(Color.GREEN);
		Comprar.setFont(new Font("Franklin Gothic Book", Font.BOLD, 13));
		Comprar.setVisible(false);
		Comprar.setBounds(10, 251, 128, 46);
		frame.getContentPane().add(Comprar);
		
		JButton Actualizar = new JButton("Actualizar");
		
		Actualizar.setVisible(false);
		Actualizar.setFont(new Font("Franklin Gothic Book", Font.BOLD, 13));
		Actualizar.setBounds(180, 251, 128, 43);
		frame.getContentPane().add(Actualizar);
		
		JButton ProductoDatos = new JButton("Producto");
		ProductoDatos.setVisible(false);
		ProductoDatos.setFont(new Font("Lucida Sans", Font.BOLD, 14));
		ProductoDatos.setBounds(67, 174, 114, 51);
		frame.getContentPane().add(ProductoDatos);
		
		JButton UsuarioDatos = new JButton("Usuario");
		
		UsuarioDatos.setFont(new Font("Lucida Sans", Font.BOLD, 14));
		UsuarioDatos.setVisible(false);
		UsuarioDatos.setBounds(269, 174, 117, 51);
		frame.getContentPane().add(UsuarioDatos);
		
		JButton Volver1 = new JButton("Volver");
		
		Volver1.setVisible(false);
		Volver1.setFont(new Font("Franklin Gothic Book", Font.BOLD, 13));
		Volver1.setBounds(180, 270, 114, 53);
		frame.getContentPane().add(Volver1);
		
		JButton Volver2 = new JButton("Volver");
		
		Volver2.setFont(new Font("Franklin Gothic Book", Font.BOLD, 13));
		Volver2.setVisible(false);
		Volver2.setBounds(180, 271, 117, 53);
		frame.getContentPane().add(Volver2);
		
		JButton Mostrar = new JButton("Mostrar");
		
		Mostrar.setFont(new Font("Franklin Gothic Book", Font.BOLD, 13));
		Mostrar.setVisible(false);
		
		JButton Volver3 = new JButton("Volver");
		
		
		Volver3.setVisible(false);
		Volver3.setBackground(Color.YELLOW);
		Volver3.setForeground(Color.RED);
		Volver3.setFont(new Font("Franklin Gothic Book", Font.BOLD, 14));
		Volver3.setBounds(190, 270, 118, 56);
		frame.getContentPane().add(Volver3);
		Mostrar.setBounds(49, 273, 100, 50);
		frame.getContentPane().add(Mostrar);
		
		
		Mostrar.addMouseListener(new MouseAdapter() {//Si deseo mostrar los datos del usuario a cambiar
			@Override
			public void mouseClicked(MouseEvent e) {
				Archivos llamar = new Archivos();
				String nombreusuario= InfoNombre.getText();
				llamar.AbrirArchivoUsuarios();
				if(nombreusuario.length()!=0){
					if(llamar.BuscarArchivoUsuarios(nombreusuario) != null){
						llamar.llenarboxes(InfoNombre,InfoApellido,InfoUsuario,InfoContra);
					}else {
						JOptionPane.showMessageDialog(null,"EL usuario a editar no se encuentra editado");
					}
				}else {
					JOptionPane.showMessageDialog(null,"Tiene que escribir un nombre.");
				}
			}				
		});
		
		JButton Guardar = new JButton("Guardar");
		Guardar.setFont(new Font("Franklin Gothic Book", Font.BOLD, 14));
		Guardar.setVisible(false);
		Guardar.setBounds(343, 271, 117, 53);
		frame.getContentPane().add(Guardar);
		SiRadio.setBackground(Color.WHITE);
		SiRadio.setForeground(Color.GREEN);
		SiRadio.setHorizontalAlignment(SwingConstants.CENTER);
		SiRadio.setBounds(269, 242, 46, 34);
		frame.getContentPane().add(SiRadio);
		
		JRadioButton NoRadio = new JRadioButton("NO");
		buttonGroup.add(NoRadio);
		NoRadio.setVisible(false);
		NoRadio.setBackground(Color.DARK_GRAY);
		NoRadio.setForeground(Color.RED);
		NoRadio.setHorizontalAlignment(SwingConstants.CENTER);
		NoRadio.setBounds(357, 242, 46, 34);
		frame.getContentPane().add(NoRadio);
		
		TextoCodigo = new JTextField();
		TextoCodigo.setVisible(false);
		TextoCodigo.setBounds(269, 61, 134, 27);
		frame.getContentPane().add(TextoCodigo);
		TextoCodigo.setColumns(10);
		
		InfoNombre = new JTextField();
		InfoNombre.setVisible(false);
		InfoNombre.setBounds(269, 97, 86, 20);
		frame.getContentPane().add(InfoNombre);
		InfoNombre.setColumns(10);
		
		InfoApellido = new JTextField();
		InfoApellido.setVisible(false);
		InfoApellido.setBounds(269, 137, 86, 20);
		frame.getContentPane().add(InfoApellido);
		InfoApellido.setColumns(10);
		
		InfoUsuario = new JTextField();
		InfoUsuario.setVisible(false);
		InfoUsuario.setBounds(269, 172, 86, 20);
		frame.getContentPane().add(InfoUsuario);
		InfoUsuario.setColumns(10);
		
		InfoContra = new JTextField();
		InfoContra.setVisible(false);
		InfoContra.setBounds(269, 213, 86, 20);
		frame.getContentPane().add(InfoContra);
		InfoContra.setColumns(10);
		
		JLabel CodigoNuevo = new JLabel("Codigo:");
		CodigoNuevo.setVisible(false);
		CodigoNuevo.setFont(new Font("Franklin Gothic Book", Font.BOLD, 16));
		CodigoNuevo.setBounds(117, 60, 74, 28);
		frame.getContentPane().add(CodigoNuevo);
		
		JLabel Infocodigo = new JLabel("");
		Infocodigo.setFont(new Font("Franklin Gothic Book", Font.BOLD, 12));
		Infocodigo.setBounds(201, 66, 74, 14);
		frame.getContentPane().add(Infocodigo);
		
		JLabel Infonombre = new JLabel("");
		Infonombre.setFont(new Font("Franklin Gothic Book", Font.BOLD, 12));
		Infonombre.setBounds(190, 91, 74, 28);
		frame.getContentPane().add(Infonombre);
		
		JLabel Infoapellido = new JLabel("");
		Infoapellido.setFont(new Font("Franklin Gothic Book", Font.BOLD, 12));
		Infoapellido.setBounds(201, 137, 46, 14);
		frame.getContentPane().add(Infoapellido);
		
		JLabel Infousuario = new JLabel("");
		Infousuario.setFont(new Font("Franklin Gothic Book", Font.BOLD, 12));
		Infousuario.setBounds(245, 175, 83, 14);
		frame.getContentPane().add(Infousuario);
		
		JLabel Infocontra = new JLabel("");
		Infocontra.setFont(new Font("Franklin Gothic Book", Font.BOLD, 12));
		Infocontra.setBounds(214, 216, 80, 14);
		frame.getContentPane().add(Infocontra);
		
		JLabel InformacionUsuario = new JLabel("INFORMACION DEL USUARIO");
		InformacionUsuario.setForeground(Color.BLUE);
		InformacionUsuario.setFont(new Font("Lucida Sans", Font.BOLD, 18));
		InformacionUsuario.setVisible(false);
		InformacionUsuario.setBounds(117, 11, 267, 42);
		frame.getContentPane().add(InformacionUsuario);
		
		JButton Volver4 = new JButton("Volver");
		
		Volver4.setForeground(Color.ORANGE);
		Volver4.setFont(new Font("Franklin Gothic Book", Font.BOLD, 13));
		Volver4.setVisible(false);
		Volver4.setBounds(190, 295, 128, 46);
		frame.getContentPane().add(Volver4);
		
		JButton CrearProducto = new JButton("Crear Producto");
		
		CrearProducto.setVisible(false);
		CrearProducto.setBackground(Color.MAGENTA);
		CrearProducto.setForeground(Color.DARK_GRAY);
		CrearProducto.setFont(new Font("Franklin Gothic Book", Font.BOLD, 12));
		CrearProducto.setBounds(166, 180, 162, 46);
		frame.getContentPane().add(CrearProducto);
		
		JButton Volver5 = new JButton("Volver");
		Volver5.setVisible(false);
		
		Volver5.setFont(new Font("Franklin Gothic Book", Font.BOLD, 13));
		Volver5.setBackground(Color.YELLOW);
		Volver5.setForeground(Color.ORANGE);
		Volver5.setBounds(180, 291, 122, 59);
		frame.getContentPane().add(Volver5);
		
		JButton Crear2 = new JButton("Crear");
		
		Crear2.setVisible(false);
		Crear2.setForeground(Color.RED);
		Crear2.setBackground(Color.DARK_GRAY);
		Crear2.setFont(new Font("Forte", Font.BOLD, 13));
		Crear2.setBounds(346, 179, 128, 42);
		frame.getContentPane().add(Crear2);
		
		JLabel codproducto = new JLabel("Codigo:");
		codproducto.setVisible(false);
		codproducto.setFont(new Font("Franklin Gothic Demi", Font.BOLD, 13));
		codproducto.setHorizontalAlignment(SwingConstants.CENTER);
		codproducto.setBounds(94, 82, 89, 37);
		frame.getContentPane().add(codproducto);
		
		JLabel nombproducto = new JLabel("Nombre:");
		nombproducto.setVisible(false);
		nombproducto.setFont(new Font("Franklin Gothic Demi", Font.BOLD, 13));
		nombproducto.setHorizontalAlignment(SwingConstants.CENTER);
		nombproducto.setBounds(104, 130, 77, 20);
		frame.getContentPane().add(nombproducto);
		
		JLabel costproducto = new JLabel("Costo:");
		costproducto.setVisible(false);
		costproducto.setFont(new Font("Franklin Gothic Demi", Font.BOLD, 13));
		costproducto.setHorizontalAlignment(SwingConstants.CENTER);
		costproducto.setBounds(104, 159, 77, 44);
		frame.getContentPane().add(costproducto);
		
		JLabel cantproducto = new JLabel("Cantidad:");
		cantproducto.setFont(new Font("Franklin Gothic Demi", Font.BOLD, 13));
		cantproducto.setVisible(false);
		cantproducto.setHorizontalAlignment(SwingConstants.CENTER);
		cantproducto.setBounds(104, 202, 90, 22);
		frame.getContentPane().add(cantproducto);
		
		codproducto2 = new JTextField();
		codproducto2.setVisible(false);
		codproducto2.setBounds(211, 91, 86, 20);
		frame.getContentPane().add(codproducto2);
		codproducto2.setColumns(10);
		
		nombproducto2 = new JTextField();
		nombproducto2.setVisible(false);
		nombproducto2.setBounds(208, 130, 86, 20);
		frame.getContentPane().add(nombproducto2);
		nombproducto2.setColumns(10);
		
		costproducto2 = new JTextField();
		costproducto2.setVisible(false);
		costproducto2.setBounds(208, 172, 86, 20);
		frame.getContentPane().add(costproducto2);
		costproducto2.setColumns(10);
		
		cantproducto2 = new JTextField();
		cantproducto2.setVisible(false);
		cantproducto2.setBounds(208, 202, 86, 20);
		frame.getContentPane().add(cantproducto2);
		cantproducto2.setColumns(10);
		
		Ingresar.addMouseListener(new MouseAdapter() {
			@Override
			public void mouseClicked(MouseEvent e) {//Cuando el usuario desee ingresar al sistema
				String Usuario2 = TextoUsuario.getText();
				String Contraseña2 = TextoContraseña.getText();
				if((Usuario2.length()!=0)&&(Contraseña2.length()!=0)) {
				boolean opcion=false;
				Archivos llamar = new Archivos();
				llamar.AbrirArchivoUsuarios();
				opcion=llamar.LeerArchivoUsuarios(Usuario2,Contraseña2);
				if(opcion!=true){
					JOptionPane.showMessageDialog(null, "El usuario no se encuentra registrado en el sistema");
					TextoUsuario.setText(null);
					TextoContraseña.setText(null);
					}else {//inicio al sistema
						JOptionPane.showMessageDialog(null,"Ha ingresado satisfactoriamente");
						
						Ingresar.setVisible(false);
						Salir.setVisible(false);
						Crear.setVisible(false);
						TextoUsuario.setVisible(false);
						TextoContraseña.setVisible(false);
						Usuario.setVisible(false);
						Contraseña.setVisible(false);
						Titulo.setVisible(false);
						Comprar.setVisible(true);
						Recargar.setVisible(true);
						Transferir.setVisible(true);
						Consultar.setVisible(true);
						Actualizar.setVisible(true);
						CrearProducto.setVisible(true);
						SalirSistema.setVisible(true);
						NombreUsuario.setVisible(true);
						MenuPrincipal.setVisible(true);
						NombreActivo.setText(llamar.BuscarArchivoUsuarios(Usuario2));
						NombreActivo.setVisible(true);	
					}
				}	
			}
		});
		
		Crear.addMouseListener(new MouseAdapter() {
			@Override
			public void mouseClicked(MouseEvent arg0) {//Cuando el usuario eliga la opcion crear usuario
				Titulo.setVisible(false);
				Salir.setVisible(false);
				Crear.setVisible(false);
				Ingresar.setVisible(false);
				Usuario.setVisible(false);
				Contraseña.setVisible(false);
				CodigoNuevo.setVisible(true);
				UsuarioNuevo.setVisible(true);
				ContraNueva.setVisible(true);
				CrearUsuarioBoton.setVisible(true);
				VolverMenu.setVisible(true);
				RegistroTitulo.setVisible(true);
				NombreNuevo.setVisible(true);
				ApellidoNuevo.setVisible(true);
				TextoNombre.setVisible(true);
				TextoApellido.setVisible(true);
				PreguntaUsuarioU.setVisible(true);
				SiRadio.setVisible(true);
				NoRadio.setVisible(true);
				TextoUsuario.setText(null);
				TextoContraseña.setText(null);
				TextoCodigo.setVisible(true);
				TextoCodigo.setText(null);
				
				
			}
		});
		
		Salir.addActionListener(new ActionListener() {
			public void actionPerformed(ActionEvent arg0) {//El programa termina con su ejecución.
				System.exit(0);
			}
		});
		
		CrearUsuarioBoton.addMouseListener(new MouseAdapter() {
			@Override 
			public void mouseClicked(MouseEvent e) { //Al crear el usuario
				
				
				if((TextoCodigo.getText().length()!=0)&&(TextoUsuario.getText().length()!=0)&&(TextoContraseña.getText().length()!=0)&&(TextoNombre.getText().length()!=0)&&(TextoApellido.getText().length()!=0)&&((SiRadio.isSelected()==true)||(NoRadio.isSelected()==true))) { 
					usuarioNuevo = TextoUsuario.getText();
					 contraseña = TextoContraseña.getText();
					 nombre = TextoNombre.getText();
					 apellido = TextoApellido.getText();	
					 codigo = TextoCodigo.getText();
					int dinerodisp=0;
					
					if(SiRadio.isSelected()==true) {
						decision="SI";
					}else {
						decision="NO";
					}
					Archivos llamar = new Archivos();
					llamar.AbrirArchivoUsuarios();
					
					llamar.EscribirArchivoUsuarios(nombre,apellido,usuarioNuevo,contraseña,dinerodisp,codigo,decision);
					llamar.CerrarArchivoUsuarios();
					JOptionPane.showMessageDialog(null,"Usuario Creado Exitosamente");
					Titulo.setVisible(true);
					Salir.setVisible(true);
					Crear.setVisible(true);
					Ingresar.setVisible(true);
					Usuario.setVisible(true);
					Contraseña.setVisible(true);
					UsuarioNuevo.setVisible(false);
					ContraNueva.setVisible(false);
					CrearUsuarioBoton.setVisible(false);
					VolverMenu.setVisible(false);
					RegistroTitulo.setVisible(false);
					NombreNuevo.setVisible(false);
					ApellidoNuevo.setVisible(false);
					SiRadio.setAction(null);
					SiRadio.setVisible(false);
					NoRadio.setAction(null);
					NoRadio.setVisible(false);
					PreguntaUsuarioU.setVisible(false);
					TextoNombre.setVisible(false);
					TextoApellido.setVisible(false);
					TextoCodigo.setVisible(false);
					TextoUsuario.setText(null);
					TextoContraseña.setText(null);
					TextoNombre.setText(null);
					TextoApellido.setText(null);	
					TextoCodigo.setText(null);
				}
			}
			
		});
		
		VolverMenu.addMouseListener(new MouseAdapter() {//Volver al menu estando desde la opcion crear usuario
			@Override
			public void mouseClicked(MouseEvent arg0) {
				Titulo.setVisible(true);
				Salir.setVisible(true);
				Crear.setVisible(true);
				Ingresar.setVisible(true);
				Usuario.setVisible(true);
				Contraseña.setVisible(true);
				TextoNombre.setVisible(false);
				TextoApellido.setVisible(false);
				TextoCodigo.setVisible(false);
				VolverMenu.setVisible(false);
				CrearUsuarioBoton.setVisible(false);
				UsuarioNuevo.setVisible(false);
				RegistroTitulo.setVisible(false);
				NombreNuevo.setVisible(false);
				CodigoNuevo.setVisible(false);
				ApellidoNuevo.setVisible(false);
				SiRadio.setVisible(false);
				NoRadio.setVisible(false);
				PreguntaUsuarioU.setVisible(false);
				TextoUsuario.setText(null);
				TextoNombre.setText(null);
				TextoApellido.setText(null);
				TextoContraseña.setText(null);
				TextoCodigo.setText(null);
				
			}
		});
		
		SalirSistema.addMouseListener(new MouseAdapter() {
			@Override
			public void mouseClicked(MouseEvent e) {// Al cerrar sesion del usuario actual
				Usuario.setVisible(true);
				Contraseña.setVisible(true);
				Salir.setVisible(true);
				Crear.setVisible(true);
				Ingresar.setVisible(true);
				Titulo.setVisible(true);
				TextoUsuario.setText(null);
				TextoUsuario.setVisible(true);
				TextoContraseña.setText(null);
				TextoContraseña.setVisible(true);
				Comprar.setVisible(false);
				Recargar.setVisible(false);
				Transferir.setVisible(false);
				Consultar.setVisible(false);
				CrearProducto.setVisible(false);
				SalirSistema.setVisible(false);
				MenuPrincipal.setVisible(false);
				Actualizar.setVisible(false);
				NombreUsuario.setVisible(false);
				NombreActivo.setVisible(false);
			}
		});
		
		Actualizar.addMouseListener(new MouseAdapter() {//Al dar al boton actualizar
			@Override
			public void mouseClicked(MouseEvent e) {
				ProductoDatos.setVisible(true);
				UsuarioDatos.setVisible(true);
				NombreUsuario.setVisible(true);
				ActualizarDatos.setVisible(true);
				Volver1.setVisible(true);
				NombreActivo.setVisible(true);
				Comprar.setVisible(false);
				Recargar.setVisible(false);
				Transferir.setVisible(false);
				Consultar.setVisible(false);
				Actualizar.setVisible(false);
				SalirSistema.setVisible(false);
				MenuPrincipal.setVisible(false);
				CrearProducto.setVisible(false);
				
			}
		});
		
		Volver1.addMouseListener(new MouseAdapter() {//Volver al menu principal estando en el menu de actualizacion
			@Override
			public void mouseClicked(MouseEvent e) {
				ProductoDatos.setVisible(false);
				UsuarioDatos.setVisible(false);
				NombreUsuario.setVisible(true);
				ActualizarDatos.setVisible(false);
				Volver1.setVisible(false);
				NombreActivo.setVisible(true);
				Comprar.setVisible(true);
				Recargar.setVisible(true);
				Transferir.setVisible(true);
				Consultar.setVisible(true);
				Actualizar.setVisible(true);
				SalirSistema.setVisible(true);
				MenuPrincipal.setVisible(true);
				CrearProducto.setVisible(true);
			}
		});
		UsuarioDatos.addMouseListener(new MouseAdapter() {//Cuando el usuario elige la opcion actualizar datos de el
			@Override
			public void mouseClicked(MouseEvent e) {
				UsuarioDatos.setVisible(false);
				ProductoDatos.setVisible(false);
				Volver1.setVisible(false);
				Volver2.setVisible(true);
				NombreNuevo.setVisible(true);
				ApellidoNuevo.setVisible(true);
				Contraseña.setVisible(true);
				Usuario.setVisible(true);
				Mostrar.setVisible(true);
				CrearProducto.setVisible(false);
				Guardar.setVisible(true);
				InfoNombre.setText(nombre);
				InfoApellido.setText(apellido);
				InfoUsuario.setText(usuarioNuevo);
				InfoContra.setText(contraseña);
				InfoNombre.setVisible(true);
				InfoApellido.setVisible(true);
				InfoUsuario.setVisible(true);
				InfoContra.setVisible(true);
			}
		});
		
		Volver2.addMouseListener(new MouseAdapter() {//Volver desde el menu de actualizar datos del usuario
			@Override
			public void mouseClicked(MouseEvent e) {
				UsuarioDatos.setVisible(true);
				ProductoDatos.setVisible(true);
				Volver1.setVisible(true);
				CrearProducto.setVisible(false);
				Volver2.setVisible(false);
				NombreNuevo.setVisible(false);
				ApellidoNuevo.setVisible(false);
				Contraseña.setVisible(false);
				Usuario.setVisible(false);
				Mostrar.setVisible(false);
				Guardar.setVisible(false);
				InfoNombre.setVisible(false);
				InfoApellido.setVisible(false);
				InfoUsuario.setVisible(false);
				InfoContra.setVisible(false);
			}
		});
		
		Consultar.addMouseListener(new MouseAdapter() {//Al consultar la informacion del usuario
			@Override
			
			public void mouseClicked(MouseEvent e) {
				SalirSistema.setVisible(false);
				Consultar.setVisible(false);
				Transferir.setVisible(false);
				Recargar.setVisible(false);
				CrearProducto.setVisible(false);
				Comprar.setVisible(false);
				Actualizar.setVisible(false);
				MenuPrincipal.setVisible(false);
				InformacionUsuario.setVisible(true);
				CodigoNuevo.setVisible(true);
				NombreNuevo.setVisible(true);
				ApellidoNuevo.setVisible(true);
				UsuarioNuevo.setVisible(true);
				Contraseña.setVisible(true);
				Volver3.setVisible(true);
				String nombre = TextoUsuario.getText();
				boolean opcion = false;
				Archivos llamado = new Archivos ();
				llamado.AbrirArchivoUsuarios();
				opcion=llamado.LeerArchivoInformacion(nombre);
				if(opcion==true) {
					llamado.llenarboxesinfo(Infocodigo,Infonombre,Infoapellido,Infousuario,Infocontra);
				}else {
					JOptionPane.showMessageDialog(null,"El usuario no se encontró.");
				}
			}
		});
					
		Volver3.addMouseListener(new MouseAdapter() {//Volver estando desde la consulta del usuario!
			@Override
			public void mouseClicked(MouseEvent e) {
				SalirSistema.setVisible(true);
				Consultar.setVisible(true);
				Transferir.setVisible(true);
				Recargar.setVisible(true);
				Comprar.setVisible(true);
				Actualizar.setVisible(true);
				MenuPrincipal.setVisible(true);
				CrearProducto.setVisible(true);
				InformacionUsuario.setVisible(false);
				CodigoNuevo.setVisible(false);
				NombreNuevo.setVisible(false);
				ApellidoNuevo.setVisible(false);
				UsuarioNuevo.setVisible(false);
				Contraseña.setVisible(false);
				Volver3.setVisible(false);
				Infocodigo.setVisible(false);
				Infonombre.setVisible(false);
				Infoapellido.setVisible(false);
				Infousuario.setVisible(false);
				Infocontra.setVisible(false);
			}
		});			
		
		Recargar.addMouseListener(new MouseAdapter() {//Al elegir recargar
			@Override
			public void mouseClicked(MouseEvent e) {
				Volver4.setVisible(true);
				SalirSistema.setVisible(false);
				Consultar.setVisible(false);
				CrearProducto.setVisible(false);
				Transferir.setVisible(false);
				Recargar.setVisible(false);
				Comprar.setVisible(false);
				Actualizar.setVisible(false);
				MenuPrincipal.setVisible(false);
				
			}
		});
		
		Volver4.addMouseListener(new MouseAdapter() {//Volver al menu estando en recargar
			@Override
			public void mouseClicked(MouseEvent e) {
				Volver4.setVisible(false);
				SalirSistema.setVisible(true);
				Consultar.setVisible(true);
				CrearProducto.setVisible(true);
				Transferir.setVisible(true);
				Recargar.setVisible(true);
				Comprar.setVisible(true);
				Actualizar.setVisible(true);
				MenuPrincipal.setVisible(true);
			}
		});
		
		
		CrearProducto.addMouseListener(new MouseAdapter() {//Al crear un producto
			@Override
			public void mouseClicked(MouseEvent e) {
				Volver5.setVisible(true);
				SalirSistema.setVisible(false);
				Consultar.setVisible(false);
				CrearProducto.setVisible(false);
				Transferir.setVisible(false);
				Recargar.setVisible(false);
				Comprar.setVisible(false);
				Actualizar.setVisible(false);
				MenuPrincipal.setVisible(false);
				codproducto.setVisible(true);
				nombproducto.setVisible(true);
				costproducto.setVisible(true);
				cantproducto.setVisible(true);
				codproducto2.setVisible(true);
				codproducto2.setText(null);
				nombproducto2.setVisible(true);
				nombproducto2.setText(null);
				costproducto2.setVisible(true);
				costproducto2.setText(null);
				cantproducto2.setVisible(true);
				cantproducto2.setText(null);
				Crear2.setVisible(true);
			}
		});
		
		Volver5.addMouseListener(new MouseAdapter() {//Devolviendose estando en crear producto
			@Override
			public void mouseClicked(MouseEvent e) {
				Volver5.setVisible(false);
				SalirSistema.setVisible(true);
				Consultar.setVisible(true);
				CrearProducto.setVisible(true);
				Transferir.setVisible(true);
				Recargar.setVisible(true);
				Comprar.setVisible(true);
				Actualizar.setVisible(true);
				MenuPrincipal.setVisible(true);
				Crear2.setVisible(false);
				codproducto.setVisible(false);
				nombproducto.setVisible(false);
				costproducto.setVisible(false);
				cantproducto.setVisible(false);
				cantproducto2.setVisible(false);
				cantproducto2.setText(null);
				costproducto2.setVisible(false);
				costproducto2.setText(null);
				nombproducto2.setVisible(false);
				nombproducto2.setText(null);
				codproducto2.setVisible(false);
				codproducto2.setText(null);
			}
		});
		
		Crear2.addMouseListener(new MouseAdapter() {//Al crear un producto
			@Override
			public void mouseClicked(MouseEvent e) {
				if((codproducto2.getText().length()!=0)&&(nombproducto2.getText().length()!=0)&&(costproducto2.getText().length()!=0)&&(cantproducto2.getText().length()!=0)) { 
					int dinerodisp=0;
					codigoproducto = codproducto2.getText();
					nombreproducto = nombproducto2.getText();
					costo = costproducto2.getText();
					cantidad = cantproducto2.getText();	
					codigo = TextoCodigo.getText();
					Archivos llamar = new Archivos();
					llamar.AbrirArchivoProductos();
					llamar.EscribirArchivoProductos(nombreproducto, codigoproducto, costo, cantidad);
					llamar.CerrarArchivoProductos();
					JOptionPane.showMessageDialog(null,"Producto Creado Correctamente");
					cantproducto2.setText(null);
					costproducto2.setText(null);
					nombproducto2.setText(null);
					codproducto2.setText(null);
					}
			}
		});
					
				
	}
}
