# UAS_PBO2

Dokumentasi UAS Form Cari Barang

/\*\*

- FormCariBarang
- \*program ini merepresentasikan antarmuka pengguna untuk pencarian barang.
- Form ini memungkinkan pengguna untuk mencari barang berdasarkan nama dan
- menampilkan hasil pencarian dalam tabel.
-
- @author USER
- @version 1.0
- @since 2024-06-26
  \*/
  package view;

import controller.controllerCariBarang;
import javax.swing.JTable;
import javax.swing.JTextField;
import model.\*;

public class FormCariBarang extends javax.swing.JFrame {

    /** Controller untuk menangani logika pencarian barang */
    controllerCariBarang cBarang;

    /**
     * Konstruktor untuk membuat form pencarian barang.
     * Menginisialisasi komponen UI, membuat instance controller,
     * dan menampilkan data awal pada tabel.
     */
    public FormCariBarang() {
        initComponents();
        cBarang = new controllerCariBarang(this);
        cBarang.tampil_tabel();
    }

    /**
     * Memperbarui tampilan tabel barang.
     * Membuat instance baru controller dan memanggil metode tampil_tabel.
     */
    public void tampilkantabel(){
        cBarang = new controllerCariBarang(this);
        cBarang.tampil_tabel();
    }

    /**
     * Mendapatkan referensi ke tabel barang.
     * @return JTable tabel barang
     */
    public JTable getTblBarang() {
        return tblBarang;
    }

    /**
     * Mengatur tabel barang.
     * @param tblBarang tabel barang yang baru
     */
    public void setTblBarang(JTable tblBarang) {
        this.tblBarang = tblBarang;
    }

    /**
     * Mendapatkan teks dari field pencarian nama barang.
     * @return JTextField field pencarian nama barang
     */
    public JTextField getTxtNamaBrg() {
        return txtCariNama;
    }

    /**
     * Mengatur teks pada field pencarian nama barang.
     * @param txtNamaBrg teks nama barang yang akan diset
     */
    public void setTxtNamaBrg(String txtNamaBrg) {
        this.txtCariNama.setText(txtNamaBrg);
    }

    // ... (kode lainnya tetap sama)

    /**
     * Event handler untuk klik pada tabel barang.
     * Belum diimplementasikan.
     */
    private void tblBarangMouseClicked(java.awt.event.MouseEvent evt) {
        // TODO: Implementasikan logika ketika baris tabel diklik
    }

    /**
     * Event handler untuk tombol Cari.
     * Memanggil metode cekNamaBrg pada controller dan memperbarui tampilan tabel.
     */
    private void btnCariActionPerformed(java.awt.event.ActionEvent evt) {
        cBarang.cekNamaBrg();
        tampilkantabel();
    }

    /**
     * Event handler untuk tombol Keluar.
     * Memanggil metode keluar pada controller.
     */
    private void btnKeluarActionPerformed(java.awt.event.ActionEvent evt) {
        cBarang.keluar();
    }

    /**
     * Metode utama untuk menjalankan aplikasi.
     * Mengatur look and feel dan menampilkan form.
     *
     * @param args argumen baris perintah (tidak digunakan)
     */
    public static void main(String args[]) {
        // ... (kode untuk mengatur look and feel)

        java.awt.EventQueue.invokeLater(new Runnable() {
            public void run() {
                new FormCariBarang().setVisible(true);
            }
        });
    }

    // Deklarasi variabel komponen UI

}
