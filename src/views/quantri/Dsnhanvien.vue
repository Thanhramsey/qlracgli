<template>
<v-container>
<v-row>
    <!-- search -->
    <v-col  md="12">
		<v-row>
			<v-col md="3">
				<v-text-field solo outlined></v-text-field>
			</v-col>
			<v-col md="3">
				<v-text-field solo outlined></v-text-field>
			</v-col>
			<v-col md="3">
				<v-text-field solo outlined></v-text-field>
			</v-col>
			<v-col md="3">
				<v-btn style="margin-top:9px" color="success">Tìm kiếm</v-btn>
			</v-col>
		</v-row>
	</v-col>
	<v-spacer></v-spacer>
</v-row>
<v-row>
  	<!-- button -->
  	<v-col cols="12" md="8">
		<v-btn class="mr-2"  color="primary" @click="dialog = true">Thêm mới</v-btn>
		<v-btn  color="error">Xóa</v-btn>
	</v-col>
	<v-spacer></v-spacer>
</v-row>
<v-row>
    	<v-simple-table dark>
			<template v-slot:default>
			<thead>
				<tr>
				<th class="text-uppercase text--primary">
					Tên nhân viên
				</th>
				<th class="text-center text-uppercase text--primary">
					Tuổi
				</th>
				<th class="text-center text-uppercase text--primary">
					Địa chỉ
				</th>
				<th class="text-center text-uppercase text--primary">
					Giới tính
				</th>
				<th class="text-center text-uppercase text--primary">
					Chức vụ
				</th>
				<th class="text-center text-uppercase text--primary">
					Tác vụ
				</th>
				</tr>
			</thead>
			<tbody>
				<tr
				v-for="item in desserts"
				:key="item.dessert"
				>
				<td>{{ item.ten }}</td>
				<td class="text-center">
					{{ item.tuoi }}
				</td>
				<td class="text-center">
					{{ item.diachi }}
				</td>
				<td class="text-center">
					{{ item.gioitinh }}
				</td>
				<td class="text-center">
					{{ item.chucvu }}
				</td>
				<td class="text-center">
					<v-btn  x-small class="mr-2"  color="primary" @click.stop="editProfile">sửa</v-btn>
				</td>
				</tr>
			</tbody>
			</template>
  		</v-simple-table>
    </v-col>
	   <v-dialog
		v-model="dialog"
		max-width="700px"
		content-class="add-dialog"
    >
      <v-card>
        <v-card-title class="dialog-header">
          <span class="text-h6">{{dialogTitle}}</span>
        </v-card-title>
        <v-card-text>
          <v-container>
            <v-row>
              <v-col
                cols="12"
                sm="6"
                md="4"
              >
                <v-text-field
                  label="Họ và tên"
                  required
				  solo
				  outlined
                ></v-text-field>
              </v-col>
              <v-col
                cols="12"
                sm="6"
                md="4"
              >
				<v-select
                  :items="['0-17', '18-29', '30-54', '54+']"
                  label="Tuổi"
                  required
				  solo
				  outlined
                ></v-select>
              </v-col>
              <v-col
                cols="12"
                sm="6"
                md="4"
              >
                <v-select
                  label="Giới tính"
				  :items="['Nam','Nữ']"
                  required
				  solo
				  outlined
                ></v-select>
              </v-col>
              <v-col
                cols="12"
                sm="6"
                md="4"
              >
                <v-select
                  label="Huyện,TP"
				  :items="['ChưPăh','Chư Sê','Chư Pưh','Pleiku']"
                  required
				  solo
				  outlined
                ></v-select>
              </v-col>
              <v-col
                cols="12"
                sm="6"
                md="4"
              >
				<v-select
                  :items="['Yên Thế','Đống Đa','Tây Sơn','Hoa Lư','Iaking','Diên Hồng','Biển Hồ','Tiên Sơn','ZADEZ']"
                  label="Phường,Xã"
                  required
				  solo
				  outlined
                ></v-select>
              </v-col>
			   <v-col
                cols="12"
                sm="6"
                md="4"
              >
                <v-text-field
                  label="Số nhà, đường"
                  required
				  solo
				  outlined
                ></v-text-field>
              </v-col>
              <v-col cols="12" class="pt-0">
                <v-text-field
                  label="Email*"
                  required
				  solo
				  outlined
                ></v-text-field>
              </v-col>
              <v-col cols="12" class="pt-0">
                <v-text-field
                  label="Password*"
                  type="password"
                  required
				  solo
				  outlined
                ></v-text-field>
              </v-col>
              <v-col
                cols="12"
                sm="6"
				class="pt-0"
              >
                <v-text-field
                  label="Số điện thoại"
                  required
				  solo
				  outlined
                ></v-text-field>
              </v-col>
              <v-col
                cols="12"
                sm="6"
				class="pt-0"
              >
                <v-select
                  :items="['Quản trị','Trưởng phòng','Nhân viên']"
                  label="Chức vụ"
				  solo
				  outlined
                ></v-select>
              </v-col>
            </v-row>
          </v-container>
        </v-card-text>
        <v-card-actions>
          <v-spacer></v-spacer>
          <v-btn
            color="error"
            @click="dialog = false"
          >
            Close
          </v-btn>
          <v-btn
            color="primary"
            @click="dialog = false"
          >
            Save
          </v-btn>
        </v-card-actions>
      </v-card>
    </v-dialog>                                        0
  </v-row>
<!-- Dialog add nhanvien -->
</v-container>

</template>

<script>
export default {
  data() {
    return {
      dialog: false,
	  dialogTitle:"Thêm mới nhân viên",
      desserts: [
        {
          ten: 'Nhân viên 1',
          tuoi: 29,
          diachi: '90 Phan Đình Phùng',
          gioitinh: 'Nam',
          chucvu: 'Trưởng phòng',
        },
        {
          ten: 'Nhân viên 2',
          tuoi: 29,
          diachi: '90 Phan Đình Phùng',
          gioitinh: 'Nam',
          chucvu: 'Trưởng phòng',
        },
        {
          ten: 'Nhân viên 3',
          tuoi: 29,
          diachi: '90 Phan Đình Phùng',
          gioitinh: 'Nữ',
          chucvu: 'Trưởng phòng',
        },
        {
          ten: 'Nhân viên 4',
          tuoi: 29,
          diachi: '90 Phan Đình Phùng',
          gioitinh: 'Nữ',
          chucvu: 'Trưởng phòng',
        },
        {
          ten: 'Nhân viên 5',
          tuoi: 29,
          diachi: '90 Phan Đình Phùng',
          gioitinh: 'Nam',
          chucvu: 'Trưởng phòng',
        },
        {
          ten: 'Nhân viên 6',
          tuoi: 29,
          diachi: '90 Phan Đình Phùng',
          gioitinh: 'Nam',
          chucvu: 'Trưởng phòng',
        },
        {
          ten: 'Nhân viên 7',
          tuoi: 29,
          diachi: '90 Phan Đình Phùng',
          gioitinh: 'Nam',
          chucvu: 'Trưởng phòng',
        },
        {
          ten: 'Nhân viên 8',
          tuoi: 29,
          diachi: '90 Phan Đình Phùng',
          gioitinh: 'Nam',
          chucvu: 'Trưởng phòng',
        },
        {
          ten: 'Nhân viên 9',
          tuoi: 29,
          diachi: '90 Phan Đình Phùng',
          gioitinh: 'Nam',
          chucvu: 'Trưởng phòng',
        },
      ],
    }
  },
  methods: {
	  editProfile(){
		  this.dialog = true;
		  this.dialogTitle ="Chỉnh sửa thông tin"
	  }
  }
}
</script>
<style lang="scss">
.v-data-table {
  width: 100%;
}

.add-dialog{
	.dialog-header {
	background-color: var(--v-primary-base);
	span {
		color: white;
	}
	}
}
</style>