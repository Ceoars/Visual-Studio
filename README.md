 private void btnHesapla_Click(object sender, EventArgs e)
        {
            double tna, ap, apd, toa, dn, don, db,am2, dap;
            tna = Convert.ToDouble(txtToplamNetAlan.Text);
            ap = Convert.ToDouble(txtArsaPay.Text);
            apd = Convert.ToDouble(txtArsaPayda.Text);
            toa = Convert.ToDouble(txtToplamOrtakAlan.Text);
            am2 = Convert.ToDouble(txtArsam2.Text);
            dn = tna * ap / apd;
            don = toa * ap / apd;
            db = dn + don;
            dap = am2 * ap / apd; 

            lblDaireNet.Text = dn.ToString();
            lblDaireBrüt.Text = db.ToString();
            lblDaireOrtakNet.Text = don.ToString();
            lblDaireninArsaPayi.Text = dap.ToString();
            //txtArsaPay.Clear();

            
            int i = dataGridView1.Rows.Add();

            dataGridView1.Rows[i].Cells[0].Value = txtDaireNo.Text;
            dataGridView1.Rows[i].Cells[1].Value = txtTapuBirimNo.Text;
            dataGridView1.Rows[i].Cells[2].Value = txtToplamNetAlan.Text;
            dataGridView1.Rows[i].Cells[3].Value = txtToplamOrtakAlan.Text;
            dataGridView1.Rows[i].Cells[4].Value = txtArsaPay.Text;
            dataGridView1.Rows[i].Cells[5].Value = txtArsaPayda.Text;
            dataGridView1.Rows[i].Cells[6].Value = lblDaireninArsaPayi.Text;
            dataGridView1.Rows[i].Cells[7].Value = lblDaireNet.Text;
            dataGridView1.Rows[i].Cells[8].Value = lblDaireOrtakNet.Text;
            dataGridView1.Rows[i].Cells[9].Value = lblDaireBrüt.Text;

            lblToplam.Text = (Convert.ToDecimal(lblToplam.Text) + Convert.ToDecimal(dataGridView1.Rows[i].Cells[9].Value)).ToString();
        }

        private void btnKapat_Click(object sender, EventArgs e)
        {
            Application.Exit();

        }

        private void btntemizle_Click(object sender, EventArgs e)
        {
            dataGridView1.Rows.Clear();
        }
    }
