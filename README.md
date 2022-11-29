# e104minhacd

Vamos criar um App para divulgar nossa CD e aprender sobre navegação em aplicativos Android.

1. Crie o conteúdo inicial a ser exixibido no App no arquico `values/strings.xml`.

```xml
<resources>
    <string name="app_name">MinhaCD</string>   
    <string name="etec_artur_nogueira">Etec Trajano Camargo</string>
    <string name="cd_cosmopolis">Celio</string>
    <string name="dev_sistemas">Dev. Sistemas</string>
    <string name="administracao">Administração</string>
    <string name="logistica">Logística</string>
    <string name="marketing">Marketing</string>
    <string name="dev_sistemas_desc">Desenvolvimento de Sistemas Web, Mobo e Desk.</string>
    <string name="administracao_desc">Administração de empresas, recursos e pessoas.</string>
    <string name="logistica_desc">Controle logístico de cadeia de produtos.</string>
    <string name="marketing_desc">Desenvolvimento de campanhas publicitárias.</string>
    <string name="lorem">Lorem ipsum dolor sit amet, consectetur adipiscing elit. Integer id euismod diam. Vestibulum mollis, nunc et sollicitudin vestibulum, ipsum eros malesuada risus, ac posuere dui libero non mi. Phasellus ut lorem sed dolor pretium efficitur tristique non felis. </string>
</resources>
```

2. Cire a interface gráfica do App no arquivo `activity_main.xml`.

```xml
<?xml version="1.0" encoding="utf-8"?>
<androidx.constraintlayout.widget.ConstraintLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:background="@color/terracota"
    tools:context=".MainActivity">

    <ImageView
        android:id="@+id/imageViewEstudante"
        android:layout_width="0dp"
        android:layout_height="0dp"
        android:adjustViewBounds="true"
        app:layout_constraintBottom_toTopOf="@+id/guidelineheader"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent"
        app:srcCompat="@drawable/ic_study"
        android:contentDescription="TODO" />

    <androidx.constraintlayout.widget.ConstraintLayout
        android:id="@+id/constraintLayout"
        android:layout_width="0dp"
        android:layout_height="0dp"
        android:background="@drawable/rounded_bg"
        android:backgroundTint="?android:attr/colorBackground"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="@+id/guidelineheader">

        <RelativeLayout
            android:id="@+id/relativeLayoutHeader"
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:layout_marginStart="16dp"
            android:layout_marginEnd="16dp"
            app:layout_constraintEnd_toEndOf="parent"
            app:layout_constraintStart_toStartOf="parent"
            app:layout_constraintTop_toTopOf="parent">

            <LinearLayout
                android:layout_width="match_parent"
                android:layout_height="wrap_content"
                android:layout_alignParentStart="true"
                android:layout_marginStart="16dp"
                android:layout_marginTop="16dp"
                android:layout_marginEnd="16dp"
                android:layout_marginBottom="16dp"
                android:orientation="vertical">

                <TextView
                    android:id="@+id/textViewEtec"
                    android:layout_width="match_parent"
                    android:layout_height="wrap_content"
                    android:text="@string/etec_cosmopolis"
                    android:textAlignment="center"
                    android:textSize="24sp"
                    android:textStyle="bold" />

                <TextView
                    android:id="@+id/textViewCD"
                    android:layout_width="match_parent"
                    android:layout_height="wrap_content"
                    android:text="@string/cd_cosmopolis"
                    android:textAlignment="center"
                    android:textSize="30sp" />

            </LinearLayout>

        </RelativeLayout>

        <LinearLayout
            android:id="@+id/linearLayoutIntents"
            android:layout_width="0dp"
            android:layout_height="wrap_content"
            android:layout_marginStart="16dp"
            android:layout_marginEnd="16dp"
            android:orientation="horizontal"
            android:weightSum="3"
            app:layout_constraintEnd_toEndOf="parent"
            app:layout_constraintStart_toStartOf="parent"
            app:layout_constraintTop_toBottomOf="@+id/relativeLayoutHeader">

            <Button
                android:id="@+id/buttonLigacao"
                style="@android:style/Widget.Material.Button.Colored"
                android:layout_width="match_parent"
                android:layout_height="wrap_content"
                android:layout_weight="1"
                android:backgroundTint="@color/terracota"
                android:drawableStart="@drawable/ic_telefone_escuro"
                android:drawableTint="@android:color/background_light"
                android:onClick="fazerLigacao"
                android:text="Ligar" />

            <Button
                android:id="@+id/buttonSite"
                style="@android:style/Widget.Material.Button"
                android:layout_width="match_parent"
                android:layout_height="wrap_content"
                android:layout_weight="1"
                android:drawableLeft="@drawable/ic_web_browser"
                android:onClick="abrirSiteEtec"
                android:text="Site" />

            <Button
                android:id="@+id/buttonEmail"
                android:layout_width="match_parent"
                android:layout_height="wrap_content"
                android:layout_weight="1"
                android:drawableLeft="@drawable/ic_email_escuro"
                android:onClick="enviarEmail"
                android:text="E-mail" />
        </LinearLayout>

        <TextView
            android:id="@+id/textViewCursos"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:layout_marginTop="8dp"
            android:text="Conheça nossos cursos"
            android:textAppearance="@style/TextAppearance.AppCompat.Large"
            app:layout_constraintEnd_toEndOf="parent"
            app:layout_constraintStart_toStartOf="parent"
            app:layout_constraintTop_toBottomOf="@+id/linearLayoutIntents" />

        <LinearLayout
            android:id="@+id/linearLayoutAdmDev"
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:layout_marginTop="8dp"
            android:orientation="horizontal"
            android:paddingStart="16dp"
            android:paddingTop="8dp"
            android:paddingEnd="16dp"
            android:paddingBottom="8dp"
            android:weightSum="2"
            app:layout_constraintEnd_toEndOf="parent"
            app:layout_constraintStart_toStartOf="parent"
            app:layout_constraintTop_toBottomOf="@+id/textViewCursos">

            <androidx.cardview.widget.CardView
                android:id="@+id/cardViewAdminstracao"
                android:layout_width="match_parent"
                android:layout_height="wrap_content"
                android:layout_marginLeft="4dp"
                android:layout_marginRight="4dp"
                android:layout_marginBottom="4dp"
                android:layout_weight="1"
                android:clickable="true"
                android:elevation="8dp"
                android:foreground="?android:attr/selectableItemBackground"
                android:onClick="abrirDetalheCurso"
                app:cardCornerRadius="4dp">

                <androidx.appcompat.widget.LinearLayoutCompat
                    android:layout_width="match_parent"
                    android:layout_height="wrap_content"
                    android:orientation="vertical">

                    <ImageView
                        android:id="@+id/imageViewAdm"
                        android:layout_width="match_parent"
                        android:layout_height="100dp"
                        android:adjustViewBounds="true"
                        android:contentDescription="TODO"
                        android:scaleType="centerCrop"
                        app:srcCompat="@drawable/administracao" />

                    <LinearLayout
                        android:layout_width="match_parent"
                        android:layout_height="wrap_content"
                        android:orientation="vertical">

                        <TextView
                            android:id="@+id/textViewAdm"
                            android:layout_width="match_parent"
                            android:layout_height="wrap_content"
                            android:gravity="center_horizontal"
                            android:text="@string/administracao"
                            android:textAppearance="@style/TextAppearance.AppCompat.Medium" />

                        <TextView
                            android:id="@+id/textViewAdmDesc"
                            android:layout_width="match_parent"
                            android:layout_height="wrap_content"
                            android:padding="8dp"
                            android:text="@string/administracao_desc"
                            android:textAppearance="@style/TextAppearance.AppCompat.Small"
                            android:textSize="12sp" />
                    </LinearLayout>
                </androidx.appcompat.widget.LinearLayoutCompat>
            </androidx.cardview.widget.CardView>

            <androidx.cardview.widget.CardView
                android:id="@+id/cardViewDevSistemas"
                android:layout_width="match_parent"
                android:layout_height="wrap_content"
                android:layout_marginLeft="4dp"
                android:layout_marginRight="4dp"
                android:layout_marginBottom="4dp"
                android:layout_weight="1"
                android:clickable="true"
                android:elevation="8dp"
                android:foreground="?android:attr/selectableItemBackground"
                android:onClick="abrirDetalheCurso"
                app:cardCornerRadius="4dp">

                <androidx.appcompat.widget.LinearLayoutCompat
                    android:layout_width="match_parent"
                    android:layout_height="wrap_content"
                    android:orientation="vertical">

                    <ImageView
                        android:id="@+id/imageViewDev"
                        android:layout_width="match_parent"
                        android:layout_height="100dp"
                        android:adjustViewBounds="true"
                        android:scaleType="centerCrop"
                        app:srcCompat="@drawable/dev" />

                    <LinearLayout
                        android:layout_width="match_parent"
                        android:layout_height="wrap_content"
                        android:orientation="vertical">

                        <TextView
                            android:id="@+id/textViewDev"
                            android:layout_width="match_parent"
                            android:layout_height="wrap_content"
                            android:gravity="center_horizontal"
                            android:text="@string/dev_sistemas"
                            android:textAppearance="@style/TextAppearance.AppCompat.Medium" />

                        <TextView
                            android:id="@+id/textViewDevDesc"
                            android:layout_width="match_parent"
                            android:layout_height="wrap_content"
                            android:padding="8dp"
                            android:text="@string/dev_sistemas_desc"
                            android:textAppearance="@style/TextAppearance.AppCompat.Small"
                            android:textSize="12sp" />
                    </LinearLayout>
                </androidx.appcompat.widget.LinearLayoutCompat>
            </androidx.cardview.widget.CardView>

        </LinearLayout>

        <LinearLayout
            android:id="@+id/linearLayoutLogMkt"
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:orientation="horizontal"
            android:paddingStart="16dp"
            android:paddingTop="8dp"
            android:paddingEnd="16dp"
            android:paddingBottom="8dp"
            android:weightSum="2"
            app:layout_constraintEnd_toEndOf="parent"
            app:layout_constraintStart_toStartOf="parent"
            app:layout_constraintTop_toBottomOf="@+id/linearLayoutAdmDev">

            <androidx.cardview.widget.CardView
                android:id="@+id/cardViewLogistica"
                android:layout_width="match_parent"
                android:layout_height="wrap_content"
                android:layout_marginLeft="4dp"
                android:layout_marginRight="4dp"
                android:layout_marginBottom="4dp"
                android:layout_weight="1"
                android:clickable="true"
                android:elevation="8dp"
                android:foreground="?android:attr/selectableItemBackground"
                android:onClick="abrirDetalheCurso"
                app:cardCornerRadius="4dp">

                <androidx.appcompat.widget.LinearLayoutCompat
                    android:layout_width="match_parent"
                    android:layout_height="wrap_content"
                    android:orientation="vertical">

                    <ImageView
                        android:id="@+id/imageViewLog"
                        android:layout_width="match_parent"
                        android:layout_height="100dp"
                        android:adjustViewBounds="true"
                        android:scaleType="centerCrop"
                        app:srcCompat="@drawable/logistica" />

                    <LinearLayout
                        android:layout_width="match_parent"
                        android:layout_height="wrap_content"
                        android:orientation="vertical">

                        <TextView
                            android:id="@+id/textViewLog"
                            android:layout_width="match_parent"
                            android:layout_height="wrap_content"
                            android:gravity="center_horizontal"
                            android:text="@string/logistica"
                            android:textAppearance="@style/TextAppearance.AppCompat.Medium" />

                        <TextView
                            android:id="@+id/textViewLogDesc"
                            android:layout_width="match_parent"
                            android:layout_height="wrap_content"
                            android:padding="8dp"
                            android:text="@string/logistica_desc"
                            android:textAppearance="@style/TextAppearance.AppCompat.Small"
                            android:textSize="12sp" />
                    </LinearLayout>
                </androidx.appcompat.widget.LinearLayoutCompat>
            </androidx.cardview.widget.CardView>

            <androidx.cardview.widget.CardView
                android:id="@+id/cardViewMarketing"
                android:layout_width="match_parent"
                android:layout_height="wrap_content"
                android:layout_marginLeft="4dp"
                android:layout_marginRight="4dp"
                android:layout_marginBottom="4dp"
                android:layout_weight="1"
                android:clickable="true"
                android:elevation="8dp"
                android:foreground="?android:attr/selectableItemBackground"
                android:onClick="abrirDetalheCurso"
                app:cardCornerRadius="4dp">

                <androidx.appcompat.widget.LinearLayoutCompat
                    android:layout_width="match_parent"
                    android:layout_height="wrap_content"
                    android:orientation="vertical">

                    <ImageView
                        android:id="@+id/imageViewMkt"
                        android:layout_width="match_parent"
                        android:layout_height="100dp"
                        android:adjustViewBounds="true"
                        android:contentDescription="TODO"
                        android:scaleType="centerCrop"
                        app:srcCompat="@drawable/marketing" />

                    <LinearLayout
                        android:layout_width="match_parent"
                        android:layout_height="wrap_content"
                        android:orientation="vertical">

                        <TextView
                            android:id="@+id/textViewMkt"
                            android:layout_width="match_parent"
                            android:layout_height="wrap_content"
                            android:gravity="center_horizontal"
                            android:text="@string/marketing"
                            android:textAppearance="@style/TextAppearance.AppCompat.Medium" />

                        <TextView
                            android:id="@+id/textViewMktDesc"
                            android:layout_width="match_parent"
                            android:layout_height="wrap_content"
                            android:padding="8dp"
                            android:text="@string/marketing_desc"
                            android:textAppearance="@style/TextAppearance.AppCompat.Small"
                            android:textSize="12sp" />
                    </LinearLayout>
                </androidx.appcompat.widget.LinearLayoutCompat>
            </androidx.cardview.widget.CardView>

        </LinearLayout>
    </androidx.constraintlayout.widget.ConstraintLayout>

    <androidx.constraintlayout.widget.Guideline
        android:id="@+id/guidelineheader"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:orientation="horizontal"
        app:layout_constraintGuide_begin="225dp" />
</androidx.constraintlayout.widget.ConstraintLayout>
```

## Continuamos na próxima aula...
