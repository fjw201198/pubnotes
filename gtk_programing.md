#GTK+\-3.0 使用笔记

###1. 去掉gtk+程序在windows下运行时的黑框框###
随便写一个测试程序  

	/* *
	 * File: helloworld.c
	 * Desc: 这是一个测试程序，改程序只有一个一个简单的窗口，
	 *       单击close按钮来关闭程序
	 */
	 int main(int argc, char *argv[]) 
	 {
	 	GtkWidget *window;
	 	gtk_init(&argc, &argv);
	 	window = gtk_window_new(GTK_WINDOW_TOPLEVEL);
	 	gtk_widget_set_request_size(window, 800, 600);
	 	g_signal_connect(window,
	 					 "destroy", 
	 					  G_CALLBACK(gtk_main_quit), 
	 					  NULL);
	 	gtk_widget_show(window);
	 	gtk_main();
	 	return 0;
	 }
	 
如果使用 `gcc -o helloworld helloworld.c $(pkg-config gtk+-3.0 --cflags --libs)` 编译，则直接双击运行时会伴随着出现一个黑乎乎的WINDOWS命令行窗口，很难看。  
去掉这个黑乎乎的窗口的方法就是在编译选项上加上 `-mwindows`，如下所示：  
	`gcc -o helloworld -mwindows helloworld.c $(pkg-confg gtk+-3.0 --cflags --libs)`
	
