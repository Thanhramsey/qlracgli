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
		<v-btn class="mr-2"  color="primary">Thêm mới</v-btn>
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
					<v-btn  x-small class="mr-2"  color="primary">sửa</v-btn>
				</td>
				</tr>
			</tbody>
			</template>
  		</v-simple-table>
    </v-col>
  </v-row>
</v-container>

</template>

<script>
export default {
  data() {
    return {
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
}
</script>
<style lang="scss">
.v-data-table {
  width: 100%;
}
</style>